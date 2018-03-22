# Techcon-Primyness-Of-Strings
find out no. of sub sequence which are prime 
package techcon.easy;

import java.util.HashSet;
import java.util.Iterator;
import java.util.Scanner;

/**
 *
 * @author AMIT
 */
public class TechconEasy {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Scanner sc=new Scanner(System.in);
        String s=sc.next();
        int i,num,j,count=0,k;
        boolean b;
        HashSet<Integer> set=new HashSet <Integer>();
       
    for(i=0;i<s.length();i++)
    {num=Integer.parseInt(s.substring(i,i+1));
    set.add(num);
    
    }
    for(i=0;i<s.length();i++)
    { for(j=i+1;j<=s.length();j++)
    { for(k=j;k<s.length();k++)
    {num=Integer.parseInt((s.substring(i,j))+s.substring(k,k+1));
    if(num<=999999)
    {set.add(num);
    System.out.println(num);
    }
    
    }}}
    Iterator <Integer>itr=set.iterator();
    while(itr.hasNext()){
    b=primecheck(itr.next());
    if(b==true)
    {
    count++;
    }
    }
    
   System.out.println(count); }
   public static boolean primecheck(int num)
    {
    int i;
    if(num==1)
    {return false;}
    else if(num==2)
    {return true;}
    else {
        for(i=2;i<=num-1;i++)
    {
    if(num%i==0)
    {
    return false;
    }
    }}
    return true;
    }
}
