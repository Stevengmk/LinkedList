# LinkedList
my JAVA codes in grade two 

public class LinkedList<Type> {

	private Node<Type> head;
	private Node<Type> tail;
	int size;
	
	
	private static class Node<Type>{

		public Type data;
		public Node<Type> link;
		
		
		 public Node(){
				
				data = null;
				link = null;
			}
			
			public Node(Type item){
				
				link = null;
				data = item;
			}
			
			public Node(Type item,Node<Type> node){
				
				data = item;
				link = node;
			}
			
			
	}
	
	
	public LinkedList(){
		
		head = new Node<Type>();
		tail = null;
		size=0;
		
	}
	
	public boolean isEmpty(){
		
		return head.link==null;
	}
	
	
	public Node<Type> find(int i){
		
		if(i<-1) return null;
		if(i==-1) return head;
		int j = 0;
		Node<Type> p = head.link;
		while(j<i&&p!=null){
			
			p = p.link;
			j++;
		}
		return p;
		
	}
	
	
	public int insert(Type value ,int i){
		
		Node<Type> p = find(i-1);
		if(p==null) return 0;
		Node<Type> newNode = new Node<Type>(value,p.link);
		if(p.link==null)
			tail = p.link;
		p.link = newNode;
		size++;
		return 1;
		
		
		
	}
	
	public Type remove(int i){
		
		Node<Type> p = find(i-1);
		if(p.link==null||p==null) return null;
		p.link = p.link.link;
		if(p.link==null)
			tail = p.link;
		size--;
		return p.link.data;
		
	}
	
	public Type get(int i){
		
		Node<Type> p = find(i);
		if(p==head||p==null)  return null;
		return p.data;
	}
	
	public Type set(Type value ,int i){
		
		Node<Type> p = find(i);
		if(p==head||p==null) return null;
		Type oldvalue = p.data;
		p.data = value;
		return oldvalue;
	}
	
	public void clear(){
		
		head = tail = null;
		size = 0;
	}
	
	public int size(){
		
		return size;
	}
	/*
	public void insert(final Type t,final int index){
		
		Node<Type> p = head;
		int k = 0;
		while(p!=null&&k<index-1){
			
			p = p.link;
			k++;
		}
		//首部插入
		
		//中间插入
		
		
	}
	
	public Node<Type> find(int i){
		
		
	}
	
	public void add(Type t,int i){
		
		Node<Type> p = find(i-1);
		if(p==null){
			
			throw new Exception();
		}
		
	p.link = new Node(t,p.link);
		
		
	}
	
	
	public void remove(int i){
		
		Node<Type> p = find(i-1);
		if(p==null||p.link==null){
			throw new Exception();
		}
		p.link = p.link.link;
	}
	
	
	//在当前结点后插入结点p
	public void insertAfter(Node<Type> p){
		
		
		
	}
	
	*/
}

