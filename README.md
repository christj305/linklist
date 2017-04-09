# linklist

import java.util.LinkedList;


public class DriverList {
    private static LinkedList origLinkedList = new LinkedList();
    private static LinkedList reversedLinkedList = new LinkedList();
    
    public static void main(String args[])
    {
        origLinkedList.add(0);
        origLinkedList.add(1);
        origLinkedList.add(2);
        origLinkedList.add(1);
        origLinkedList.add(0);
        
        if(isPalindrome(origLinkedList))
        {
            System.out.println("0-> 1 -> 2 -> 1 -> 0");
            System.out.println("List is plaindrome");
        }
        
        origLinkedList.clear();
        
        
        origLinkedList.add(2);
        origLinkedList.add(1);
        origLinkedList.add(2);
        origLinkedList.add(1);
        origLinkedList.add(0);
        if(!isPalindrome(origLinkedList))
        {
            System.out.println("2-> 1 -> 2 -> 1 -> 0");
            System.out.println("List is not palindrome");
        }
    }
    
    public static boolean isPalindrome(LinkedList head)
    {
        //Reverse the linked lis   
        LinkedList reverseList = reverseAndClone(head);
        return isEqual(reverseList, origLinkedList);
    }
    
   public static LinkedList reverseAndClone(LinkedList aLL) {
        for(int i=aLL.size()-1;i>=0;i--)
        {
            reversedLinkedList.add(aLL.get(i));
        }
        return reversedLinkedList;
    }
    public static boolean isEqual(LinkedList one, LinkedList two)
    {
        if(one.size()!=two.size())
        {
            return false;
        }
        for(int i=0;i< one.size();i++)
        {
            if(one.get(i)!=two.get(i))
            {
                return false;
            }
        }
        return true;
    }
}
