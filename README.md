Arrays are Disjoint or Not in Java
Here, in this page we will discuss the program to find whether the given arrays are disjoint or not in java programming language. Two arrays are said to be disjoint if the intersection of the array is empty.

Disjoint array java
Method Discussed :
Method 1 : Using Naive approach.
Method 2 : Using sorting and hashing
Method 3 : Using Hashing
Method 1 :
Run a loop from index 0 to n
Run a nested loop from 0 to m
Check if (arr1[i]==arr2[j]) return 0.
Otherwise, return 1.
Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in Java
import java.util.*;
 
class Main
{
    // This function prints all distinct elements
    static boolean Disjoint(int arr1[], int arr2[])
    {
        
        for(int i=0; i<arr1.length; i++){
        for(int j=0; j<arr2.length; j++){
            if(arr1[i]==arr2[j]){
                return false;   
            }
        }
    }
    return true;
    }
 
    // Driver method to test above method
    public static void main (String[] args)
    {
        int arr1[] = {10, 51, 3, 43, 6};
        int arr2[] = {80, 71, 29, 3};
        
        if (Disjoint(arr1, arr2))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}
Output :
No
Method 2 :
In this method first sort both the given integer arrays, then using the merge process we compare the elements in both arrays.

Related Pages
Find all Symmetric pairs in an array

Find maximum product sub-array in a given array

Determine Array is a subset of another array or not

Determine can all numbers of an array be made equal

Finding Minimum sum of absolute difference of given array

Method 2 : Code in Java
import java.util.*;
 
class Main
{
    // This function prints all distinct elements
    static boolean Disjoint(int arr1[], int arr2[])
    {
       int i=0,j=0;
         
        // Sort the given two sets
        Arrays.sort(arr1);
        Arrays.sort(arr2);
         
        // Check for same elements using
        // merge like process
        while(iarr2[j])
                j++;
            else
                return false;
             
        }
        return true;
    }
 
    // Driver method to test above method
    public static void main (String[] args)
    {
        int arr1[] = {10, 51, 3, 43, 6};
        int arr2[] = {80, 71, 29, 3};
        
        if (Disjoint(arr1, arr2))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}    
Output :
No
Method 3 :
In this method we use the concept of hashing.

Iterate through the first array and store every element in the hash table.
Iterate through the second array and check if any element is present in the hash table.
If present, then returns false, else ignore the element. 
If all elements of the second array are not present in the hash table, return true.
Method 3 : Code in Java
import java.util.*;
 
class Main
{
    // This function prints all distinct elements
    static boolean Disjoint(int arr1[], int arr2[])
    {
       HashSet set = new HashSet<>();
 
        // Traverse the first set and store its elements in hash
        for (int i=0; i<arr1.length; i++)
            set.add(arr1[i]);
 
        // Traverse the second set and check if any element of it
        // is already in hash or not.
        for (int i=0; i<arr2.length; i++)
            if (set.contains(arr2[i]))
                return false;
 
        return true;
    }
 
    // Driver method to test above method
    public static void main (String[] args)
    {
        int arr1[] = {10, 51, 3, 43, 6};
        int arr2[] = {80, 71, 29, 3};
        
        if (Disjoint(arr1, arr2))
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}    
Output :
No
