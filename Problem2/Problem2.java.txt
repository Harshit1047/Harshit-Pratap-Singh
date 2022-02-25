import java.lang.*;
import java.util.*;
public class Prefix{
	
	static final int maximum = 456;
	static final int maximum_word_length = 800;
	
	static class Trie
	{
		Trie[] child = new Trie[maximum];
		int frequency; 
		Trie() {
			frequency =1;
			for (int i = 0; i < maximum; i++)
				child[i] = null;
		}
	}
	static Trie root;
	static void insert(String str)
	{
		int len = str.length();
		Trie pCrawl = root;
		for (int lev = 0; lev<len; lev++)
		{
			int index = str.charAt(lev);
			if (pCrawl.child[index] == null)
				pCrawl.child[index] = new Trie();
			else
			(pCrawl.child[index].frequency)++;
			pCrawl = pCrawl.child[index];
		}
	}
	static void prefixFindUtil(Trie root, char[] prefix,
						int ind)
	{
		if (root == null)
		return;
		if (root.frequency == 1)
		{
		prefix[ind] = '\0';
		int i = 0;
		while(prefix[i] != '\0')
			System.out.print(prefix[i++]);
		System.out.print(" ");
		return;
		}
	
		for (int i=0; i<maximum; i++)
		{
		if (root.child[i] != null)
		{
			prefix[ind] = (char) i;
			prefixFindUtil(root.child[i], prefix, ind+1);
		}
		}
	}
	static void prefixFind(String arr[], int n)
	{
		root = new Trie();
		root.frequency = 0;
		for (int i = 0; i<n; i++)
			insert(arr[i]);
		char[] prefix = new char[maximum_word_length];
		prefixFindUtil(root, prefix, 0);
	}
	public static void main(String args[])
	{
		String arr[] = {"bonfire", "found", "bonf"};
		int n = arr.length;
		prefixFind(arr, n);
	}
}



