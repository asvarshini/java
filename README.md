##This project demonstrates the use of Java Generics to sort arrays of different data types using a single generic method.
It uses bounded type parameters (Comparable) to ensure type safety and applies bubble sort to sort product names (String) and product prices (Double).

The program also includes a generic method to print array elements and allows user selection through console input.

import java.util.Scanner;
class  Main
{
public static <T extends Comparable<T>> void sortArray(T[] array)
{
int n = array.length;
T  temp;
for(int i =0;i<n-1;i++)
{

for(int j=0;j<n-i-1;j++)
{
if(array[j].compareTo(array[j+1])>0)
{
temp =array[j];
array[j] =array[j+1];
array[j+1] =temp;
}
}
}
}
public static <T> void printArray(T[] array)
{
for(T elements:array)
{
System.out.println(elements );
}
System.out.println();
}

public static void main(String args[])
{
Scanner ob =new Scanner(System.in);
String[] name={"cherry","apple","mango","bannna"};
Double[] price ={20.0,100.0,120.0,60.0};
System.out.println("enter 1. sort name(product name)  \n 2 . sort price(product price) \n enter the choice(1 or 2)");
int choice = ob.nextInt();
switch(choice)
{
case 1:
System.out.printf(" product name before sorting \n");
printArray(name);
sortArray(name);

System.out.printf("product name before sorting \n");
printArray(name);
break;
case 2:
System.out.printf(" product price before sorting \n");
printArray(price);
sortArray(price);

System.out.printf("product name before sorting \n");
printArray(price);
break;
}}}
