2019-3-10

	public class text2 {
	    public static void main(String[] args) {
	
	        int a,b,c;
	        for(int i = 100 ; i <1000;i++) {
	            a=i%10;
	            b=(i/10)%10;
	            c=i/100;
	            if(i==a*a*a+b*b*b+c*c*c){
	                System.out.println(i);
	            }
	        }
	    }
	}
	public class text {
	    public static void main(String[] args) {
	        int max = Integer.MAX_VALUE;
	        int min = Integer.MIN_VALUE;
	        System.out.println(max);
	        System.out.println(min);
	        System.out.println(max+1L);
	        System.out.println(min-(long)1);
	        System.out.println((long)min-2);
	        //小范围类型加大范围类型自动转化为大范围类型
	    }
	}
#
	public class text2 {
	    public static void main(String[] args) {
	        int a = 2;
	        int b = 3;
	        int t;
	        t=a;
	        a=b;
	        b=t;
	        System.out.println(a);
	        System.out.print(b);
		}
	}
#
	public class text2 {
	    public static void main(String[] args) {
	        int sum=0;
	        for(int i=100;i<=200;i++){
	            sum+=i;
	        }
	        System.out.println(sum);
	    }
	}
#	
	public class text2 {
	    public static void main(String[] args) {
	        int sum=0;
	        int i=100;
	        while(i<=200){
	            sum+=i;
	            i++;
	        }
	        System.out.println(sum);
	    }
	}
#
	public class text2 {
	    public static void main(String[] args) {
	        int sum=0;
	        int i=100;
	        do {
	            sum+=i;
	            i++;
	        }while(i<=200);
	        System.out.println(sum);
	    }
	}
#
		class Member{
	    private int mid;
	    private  String name;
	    private  Car car;
	    private  Member child;
	    public Member(int mid,String name){
	        this.mid=mid;
	        this.name=name;
	    }
	    public void setCar(Car car){
	        this.car=car;
	    }
	    public Car getCar(){
	        return this.car;
	    }
	
	    public void setChild(Member child) {
	        this.child = child;
	    }
	
	    public Member getChild() {
	        return child;
	    }
	    public String getInfo(){
	        return "人员编号："+this.mid+",姓名："+this.name;
	    }
	}
	class Car{
	    private Member member;
	    private  String pname;
	    public Car(String pname){
	        this.pname=pname;
	    }
	    public void setMember(Member member){
	        this.member=member;
	    }
	    public Member getMember(){
	        return this.member;
	    }
	    public String getInfo(){
	        return "车的名字："+this.pname;
	    }
	}
	public class text1 {
	    public static void main(String[] args) {
	        Member m=new Member(1,"李兴华");
	        Member chd=new Member(2,"李闯");
	        Car c=new Car("八手奥拓100");
	        Car cc=new Car("法拉利M9");
	        m.setCar(c);
	        c.setMember(m);
	        chd.setCar(cc);
	        cc.setMember(chd);
	        m.setChild(chd);
	        System.out.println(m.getCar().getInfo());
	        System.out.println(c.getMember().getInfo());
	        System.out.println(m.getChild().getInfo());
	        System.out.println(m.getChild().getCar().getInfo());
	    }
	}
#
	class Man{
	    private String  num;
	    private String name;
	    private  String sex;
	    public Man(String num,String name,String sex) {
	        this.num=num;
	        this.name=name;
	        this.sex=sex;
	    }
		public void setNum(String num) {
	        this.num = num;
	    }
	
	    public void setName(String name) {
	        this.name = name;
	    }
	
	    public void setSex(String sex) {
	        this.sex = sex;
	    }
	
	    public String getNum() {
	        return num;
	    }
	
	    public String getName() {
	        return name;
	    }
	
	    public String getSex() {
	        return sex;
	    }
	    public String getInfo(){
	        return "学号："+num+"\t\t"+"名字："+name+"\t\t"+"性别："+sex;
	    }
	}
	public class text2 {
	    public static void main(String[] args) {
	        Man man=new Man("04184003","张晓龙","男");
	        System.out.println(man.getInfo());
	    }
	}
#
	class Node{
	    private String data;
	    private  Node next;
	    public Node(String data){
	        this.data=data;
	    }
	    public void setNext(Node next){
	        this.next=next;
	    }
	    public  Node getNext(){
	        return this.next;
	    }
	    public  String getData(){
	        return this.data;
	    }
	    public void addNode(Node newNode){
	        if(this.next==null){
	            this.next=newNode;
	        }else{
	            this.next.addNode(newNode);
	        }
	    }
	    public void printNode(){
	        System.out.print(this.data);
	        if(this.next != null){
	            this.next.printNode();
	        }
	    }
	}
	class Link{
	    private Node root;
	    public void add(String data){
	        Node newNode=new Node(data);
	        if(this.root==null){
	            this.root = newNode;
	        }else{
	            this.root.addNode(newNode);
	        }
	    }
	    public void print(){
	        if(this.root!=null){
	            this.root.printNode();
	        }
	    }
	}
	public class test3{
	    public static void main(String[] args) {
	        Link link= new Link();
	        link.add("Hello");
	        link.add(",what");
	        link.add(" is your name?");
	        link.print();
	    }
	}
#
	class Array{
	    private int data[];
	    private int foot;
	    public Array(int len) {
	        if (len > 0) {
	            this.data = new int[len];
	        } else {
	            this.data = new int[1];
	        }
	    }
	    public boolean add(int num){
	        if(this.foot<this.data.length){
	            this.data[this.foot++]=num;
	            return true;
	        }else{
	            return false;
	        }
	    }
		public int[] getData() {
	        return data;
	    }
	}
	public class test4{
	    public static void main(String[] args) {
	        Array arr=new Array(3);
	        System.out.print(arr.add(20)+"、");
	        System.out.print(arr.add(10)+"、");
	        System.out.print(arr.add(30)+"、");
	        System.out.print(arr.add(100)+"、");
	        int[] temp=arr.getData();
	        for(int x=0;x<temp.length;x++){
	            System.out.print(temp[x]+"、");
	        }
	    }
	}
#
	class A{
	    public void print(){
	        System.out.println("A、public void print()");
	    }
	}
	class B extends A{
	    public void print(){
	        System.out.println("B、public void print()");
	    }
	}
	class C extends A{
	    public void print(){
	        System.out.println("C、public void print()");
	    }
	}
	public class test5 {
	    public static void main(String[] args) {
	        A a=new B();
	        a.print();
	        A b=new C();
	        b.print();
	    }
	}
#
	class Outer{
	    private String msg="Hello World !";
	    public void fun(){
	        new Inner(this).print();
	    }
	    public String getMsg(){
	        return this.msg;
	    }
	}
	class Inner{
	    private Outer out;
	    public Inner(Outer out){
	        this.out=out;
	    }
	    public void print(){
	        System.out.println(this.out.getMsg());
	    }
	}
	public class test6 {
	    public static void main(String[] args) {
	        Outer out=new Outer();
	        out.fun();
	    }
	}

