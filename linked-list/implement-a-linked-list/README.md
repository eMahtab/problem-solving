# Implement a Linked List

```java
import java.util.NoSuchElementException;

public class LinkedList {
	
	private class Node {
		int data;
		Node next;
		
		Node(int data){
			this.data = data;
		}
	}
    private Node head;
    private int size;
    
    public LinkedList(){
    }
    
    public void add(int value) {
    	Node node = new Node(value);
    	if(head == null)
    	  head = node;
    	else {
    		Node current = head.next;
    		Node prev = head;
    		while(current != null) {
    			prev = current;
    			current = current.next;
    		}
    		prev.next = node;
    	}
    	size++;
    }
    
    public int removeFirst() {
    	if(head == null)
    		throw new NoSuchElementException("Error : List is empty");
    	int val = head.data;
    	head = head.next;
    	size--;
    	return val;
    }
    
    public boolean remove(int value) {
    	if(head == null)
    		return false;
    	
    	Node current = head;
    	Node prev = null;
    	while(current != null) {
    		if(current.data == value) {
    			if(prev == null)
    				head = head.next;
    			else
    			    prev.next = current.next;
    			size--;
    			return true;
    		}
    		prev = current;
    		current = current.next;
    	}
    	return false;
    }
    
    public int size() {
    	return size;
    }
    
    public String toString() {
    	StringBuilder str = new StringBuilder("[");
    	Node current = head;
    	
    	while(current != null) {
    		str.append(current.data);
    		current = current.next;
    		if(current != null)
    		  str.append(", ");
    	}
    	str.append("]");
    	return str.toString();
    }
}

```


## Test  :
```java
public class App {

	public static void main(String[] args) {

		LinkedList list = new LinkedList();
		
		list.add(1); list.add(2); list.add(3);
		System.out.println("List :" + list);
		
		list.remove(3);
		System.out.println(list);
		
		list.add(4); list.add(1); list.remove(1);
		System.out.println(list);
		
		list.remove(4);
		System.out.println(list);
		
		System.out.println("Removing all elements one by one :");
		while(list.size() > 0) {
			list.removeFirst();
		}
		System.out.println(list);
	}
}
```

## Output :
```
List :[1, 2, 3]
[1, 2]
[2, 4, 1]
[2, 1]
Removing all elements one by one :
[]
```