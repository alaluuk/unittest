# Xunit example

Create a GitHub repo and clone it. Then execute **dotnet new console**

## Add Xunit

Execute command
<pre>
dotnet add package xunit
</pre>

Replace the Program.cs with below code 
<pre>
Console.WriteLine("Xunit Example");
Console.WriteLine("5 plus 6 = "+Sum(5,6));

int Sum(int a, int b){
    return a+b;
}
</pre>

Add a file named **UnitTest.cs** with below code 
<pre>
using Xunit;
public class UnitTest
{
    [Fact]
    public void Test1()
    {
        {
            Assert.Equal(11, Sum(5, 6));
        }
    }

        [Fact]
    public void Test2()
    {
        {
            Assert.Equal(12, Sum(6, 7));
        }
    }

    int Sum(int a, int b){
        return a+b;
    }
}
</pre>

## Execute tests

<ol>
<li>Execute command **dotnet test**</li>
<li>Edit one of the Sum-method so that it will return a-b and execute the test again </li>
</ol>

## GitHub Actions

In GitHub choose **Actions** and then **.NET ->Configure ->Start Commit**

And in your local repo **pull* and then try 
<ol>
<li>Make some changes that fill cause the tests to **fail** and push to GitHub and check Actions</li>
<li>Make some changes that fill cause the tests to **pass** and push to GitHub and check Actions</li>
</ol>