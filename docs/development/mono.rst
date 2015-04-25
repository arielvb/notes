Mono
====

:url: http://www.mono-project.com/
:docs: http://www.mono-project.com/docs/
:api: http://docs.go-mono.com/
:tags: programming language, opensource, .net


Mono appeared on 2004 as a crossplatform .NET framework opensource implementation.

.. note::

    This documents covers only C# features of Mono.


Building your sources with the commandline
------------------------------------------

If your sources have a `.csproj/.sln file` you can use `mdtool` to build it, if not you can compile it with `Mono C# compiler (mcs)`.

Using the Mono C# compiler: mcs
++++++++++++++++++++++++++++++++
:url: http://linux.die.net/man/1/mcs

Lets supose you have a single source `hello.cs`, with the following content:

.. code-block:: c#

    using System;

    class Hello {

        static void Main() {
            Console.WriteLine ("Hello, World!");
        }

    }

You can build it running:

    mcs example.cs

Using MonoDevelop: mdtool
+++++++++++++++++++++++++

To obtain mdtool, you will have to install MonoDevolop or Xamarin Studio.

Code analizers
++++++++++++++

Assembly analizer: gendarme

After running `gendarme` on our example `hello.cs`::

    mcs hello.cs && mono gendarme.exe hello.exe

We will see a listing with all the defects in our assebly, after fixing them our code will look like:

.. code-block:: c#

    using System;
    using System.Reflection;
    using System.Runtime.InteropServices;

    [assembly: CLSCompliant (true)]
    [assembly: ComVisible (false)]
    [assembly: AssemblyVersion ("1.0.0.0")]

    static class Hello {

        static void Main() {

            Console.WriteLine ("Hello, World!");

        }
    }


Documenting your code
+++++++++++++++++++++

If some one else needs to use your code, you probably should to generate some documentation for your classes, methods one great tool is `Doxygen <http://www.stack.nl/~dimitri/doxygen/>`_.

UML
....

`Doxygen` can generate some basic UML diagrams, if you want the big picture you can try to use `NClass <http://nclass.sourceforge.net/>`_


Code coverage
+++++++++++++

`OpenCover <https://github.com/sawilde/opencover>`_


Reports
.......

After running the codecoverage for your tests probably you want to create a report, you can use `ReportGenerator <http://danielpalme.github.io/ReportGenerator/>`_


Continuous integration
++++++++++++++++++++++

You can use `Jenkins <http://developer.xamarin.com/guides/cross-platform/ci/jenkins_walkthrough/>`_, `SonarCube <http://www.wrightfully.com/setting-up-sonar-analysis-for-c-projects/>`_.


References
----------

- `Introduction to Mono - Your first Mono app <http://www.codeproject.com/Articles/9407/Introduction-to-Mono-Your-first-Mono-app>`_
- `C# compiler Command-line options <http://old.kov.eti.br/programacao/mono/handbook/tools/cscomp-cmdlo.html>`_
- `Walkthrough: Creating an MSBuild Project File from Scratch <https://msdn.microsoft.com/en-us/library/vstudio/dd576348%28v=vs.100%29.aspx>`_

Extras
------

- `Using Maven with .NET <http://docs.codehaus.org/display/MAVENUSER/Using+Maven+to+manage+.NET+projects>`_
