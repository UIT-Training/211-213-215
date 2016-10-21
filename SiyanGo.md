###一 . 前言 
最近在学习Rxjava和观察者模式，首先回顾一下接口回调。

###二.回调函数
回调就是在类A中调用B类中的某个方法C之后，当C处理完完之后再去调用A中的D方法


###三.具体实现
举个例子：学生去向老师询问问题，老师有时间的时候，去告诉学生。

```public interface CallBack {	//实现回调的接口	public void response(String qusetion);}```

```public class Student implements CallBack{		private Teacher teacher;			//学生问老师问题	public void askTeacher(Teacher teacher,String question){						teacher.receive(this, question);			}			//得到老师的回复	@Override	public void response(String answer) {		// TODO Auto-generated method stub		System.out.println("The answer is"+answer);			}	    //学生做别的事情	public void play() {				System.out.println("play....");	}		}```

```public class Teacher {		public void receive(CallBack callBack,String question){								System.out.println("The question is "+question);						new Thread(new Runnable() {						@Override			public void run() {				// TODO Auto-generated method stub				//do other things				try {										//老师忙完之后回复学生					Thread.sleep(4096);					callBack.response("2");				} catch (InterruptedException e) {					// TODO Auto-generated catch block					e.printStackTrace();				}							}		}).start();									}				}```

```public class Test {	public static void main(String[] args) {		// TODO Auto-generated method stub		Student student=new Student();		Teacher teacher=new Teacher();		student.askTeacher(teacher,"1+1=?");		student.play();	}}```