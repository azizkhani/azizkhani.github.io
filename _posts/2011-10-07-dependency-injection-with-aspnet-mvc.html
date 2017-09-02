---
layout: post
title: "Dependency Injection  with ASP.NET MVC"
comments: true
---
<h1>Dependency Injection&nbsp; with ASP.NET MVC</h1>
<p>&nbsp;</p>
<div class="abstract">As you delve more into ASP.NET MVC you start to come across a whole new way of doing things that Web Forms development didn't really expose you to. Inversion of Control (IoC) and Dependency Injection (DI) are two phrases that crop up a lot in the MVC space. So what are they all about? And should you care?</div>
<p>&nbsp;</p>
<p>I should start by stating the IoC and DI are not unique to ASP.NET MVC. They have been around a long time. It's just that MVC supports these notions particularly well. IoC is a principle, or an architectural pattern. There are quite a few definitions of IoC, but the basis behind it is always the same - it helps towards a loosely coupled architecture. DI is one way in which IoC can be applied, according to one school of thought.&nbsp; DI <em>is</em> IoC according to another. So far, you may be none the wiser, so I will use a bit of code based on the <a href="http://www.asp.net/learn/mvc/#MVC_SampleApp">Contact Manager ASP.NET MVC tutorial</a> to help illustrate the basic problem that they or it are/is intended to solve:</p>
<pre class="code"><span style="color: blue;">public class </span><span style="color: #2b91af;">ContactController </span>: <span style="color: #2b91af;">Controller </span>{
  <span style="color: blue;">private </span><span style="color: #2b91af;">ContactManagerModelDataContext </span>entities = <span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerModelDataContext</span>();

  <span style="color: blue;">public </span><span style="color: #2b91af;">ActionResult </span>Index()
  {
    <span style="color: blue;">return </span>View(entities.Contacts.ToList());
  }
}  

<span style="color: blue;">public class </span><span style="color: #2b91af;">ContactController </span>: <span style="color: #2b91af;">Controller </span>{
  <span style="color: blue;">private </span><span style="color: #2b91af;">ContactManagerEntities </span>entities = <span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerEntities</span>();

  <span style="color: blue;">public </span><span style="color: #2b91af;">ActionResult </span>Index()
  {
    <span style="color: blue;">return </span>View(entities.ContactSet.ToList());
  }
}

</pre>
<p>Just to clear up any initial confusion, yes - the example above is more or less the same code twice. One uses LINQ to SQL (the first one) and the second uses the Entity Framework for data access. Both versions have a dependency on the data access service or layer, in that neither controller can do their thing without it. However, in both versions, the specifics of the dependency is hardcoded into the Controller. That's called "Tight Coupling". In the first version, a LINQ to SQL DataContext is instantiated and referenced, and a <span class="black">System.Data.Linq.Table&lt;T&gt;</span> object is passed to the View. In the second, an Entity Framework ObjectContext is referenced, and a <span class="black">System.Data.Object.ObjectQuery&lt;T&gt;</span> is passed to the View.</p>
<p>There is no separation of concerns here in that the data access layer is embedded in the Controller. So what's the problem with that? Well, imagine that the two versions are an example of "before" and "after". In other words, you began by using LINQ to SQL, and then were required to change the data access to the Entity Framework (or ADO.NET, nHibernate, Typed DataSets or any number of other methods). OK, you think - it's just a couple of lines that were changed. Now imagine that these Controllers had 20 or 30 Actions, and that there are 20 or 30 Controllers. Now you begin to see the problem...</p>
<p>"Oh, but that will never happen to me", you say. And I can to an extent sympathise with that: the only data access changes I have ever made to an application were through my own choice. Until a couple of weeks ago. We weren't expecting it at all. But it happened nevertheless and was forced on us.</p>
<p>When you view Data Access as a "component" of your application, you should also start to see that there are other areas in an application which could be viewed as components. An emailing service, a logging service, caching, validation etc. All of these could be implemented as components. You may already be using ready-built components such as those found within the Enterprise Library. They could all potentially become dependencies of Controllers or even eachother. And all could be subject to change. You might decide to experiment with one, and then after some work, decide it doesn't suit you, so you need to exchange it for another. Now <em>that</em> happens to me quite often.</p>
<p>Another problem with the tightly coupled examples is with Unit Testing. If you are taking the trouble to read this article and haven't got round to a structured testing regime for your applications yet, chances are that you will. At the moment, if you write a test for the Index Action of the ContactController, you will cause a call to the database. If you take a Test Driven Design approach, you probably won't even <em>have</em> a database at this point, let alone any useful data in it. And if you have created a database, you need to stuff it with dummy data so that it can return something tangible. And testing against databases (when you have hundreds of automated tests to run) is slow. So you create a Mock. A mock in this case is service that simulates or mimics the database. It will generate collections for you, but you need to replace the data access code in the Controller so that the Controller is dependent on the mock object instead of connecting to and querying the database. And you need to do that every time you run the tests, and then undo it again, which will be time-consuming and messy.</p>
<h5>Dependency Injection</h5>
<p>Inversion of Control really describes what happens when you move away from a procedural programming style, where each line of code is run in turn, to a more (for example) event-driven style, where code is fired as a result of external factors. In other words, in procedural programming, control of what happens and when is entirely in the hands of the programmer. In an event-driven application, the control over what happens and when is inverted or placed in the hands of the user. One of the benefits of moving away from a procedural approach to a more object-oriented style of applications development is that you need a lot less boilerplate or repetitive code. In a procedural application, if there was a need to make 4 calls to a database within a function, you would have to write code to connect to the database and interact with it 4 times. When you run the programme, it will run from top to bottom. The code is entirely in control of that. Taking a more abstract approach allows you to write the database code once (as a service or component), and to provide a means of supplying it to the function that needs it at the point it is needed (if at all). In other words, the dependency (the data service) is injected into the calling function.</p>
<p>It's a bit like the difference between having to walk around with this lot in your toolbag:</p>
<p><img src="/IMAGES/2011/10/interface2.jpg.jpgx" alt="" /></p>
<p>and this:</p>
<p><img src="/IMAGES/2011/10/interface.jpg.jpgx" alt="" /></p>
<p>Imagine that the main body of the tool in the second image is a Controller. Each of the attachments that plug into it are different data access components. One is for LINQ to SQL, one for the Entity Framework and the last one uses nHibernate internally. The reason that they can so easily be swapped in and out is that they all share a common interface with the main body of the tool. The main body has been designed to expect a component that has been tooled to fit. So long as additional attachments implement the correct interface, there is no reason why you can't build a lot more - a toothbrush, for example, or an egg whisk - and be sure that they will all fit. Ok - this example isn't perfect: the attachment or component is not providing a service to the body of the tool so the analogy falls down a little, but the principle behind common interfaces should be clear.</p>
<p>This brings us onto a key Design Principal - Code to an Interface, not an Implementation.</p>
<p>Right. First, we need an interface, which will define the methods that the data access component will implement. In this example, there is only one method so far:</p>
<pre class="code"><span style="color: blue;">public interface </span><span style="color: #2b91af;">IContactRepository </span>{
  <span style="color: #2b91af;">IList</span>&lt;<span style="color: #2b91af;">Contact</span>&gt; GetContacts();
}

</pre>
<p>Now we move the actual data access out of the Controller into a separate class that implements the IContactRepository interface:</p>
<pre class="code"><span style="color: blue;">public class </span><span style="color: #2b91af;">ContactManagerLinqRepository </span>: <span style="color: #2b91af;">IContactRepository </span>{
  <span style="color: blue;">public </span><span style="color: #2b91af;">IList</span>&lt;<span style="color: #2b91af;">Contact</span>&gt; GetContacts()
  {
    <span style="color: #2b91af;">ContactManagerModelDataContext </span>entities = <span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerModelDataContext</span>();
    <span style="color: blue;">return </span>entities.Contacts.ToList();
  }
}

</pre>
<p>This particular example uses LINQ to SQL, but the Entity Framework version is very similar:</p>
<pre class="code"><span style="color: blue;">public class </span><span style="color: #2b91af;">ContactManagerEntityRepository </span>: <span style="color: #2b91af;">IContactRepository </span>{
  <span style="color: blue;">public </span><span style="color: #2b91af;">IList</span>&lt;<span style="color: #2b91af;">Contact</span>&gt; GetContacts()
  {
    <span style="color: #2b91af;">ContactManagerEntities </span>entities = <span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerEntities</span>();
    <span style="color: blue;">return </span>entities.ContactSet.ToList();
  }
}

</pre>
<p>If we go back to the Controller, the change required to make use of the Entity Framework version is as follows:</p>
<pre class="code"><span style="color: blue;">public class </span><span style="color: #2b91af;">ContactController </span>: <span style="color: #2b91af;">Controller </span>{
  <span style="color: blue;">private readonly </span><span style="color: #2b91af;">IContactRepository </span>iRepository;

  <span style="color: blue;">public </span>ContactController() : <span style="color: blue;">this</span>(<span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerEntityRepository</span>())
  {}

  <span style="color: blue;">public </span>ContactController(<span style="color: #2b91af;">IContactRepository </span>repository)
  {
    iRepository = repository;
  }

  <span style="color: blue;">public </span><span style="color: #2b91af;">ActionResult </span>Index()
  {
    <span style="color: blue;">return </span>View(iRepository.GetContacts());
  }
}

</pre>
<p>When the parameterless constructor is called, it automatically calls the second constructor that has the IContactRepository parameter. That's what the <span class="code">: <span style="color: blue;">this</span>(<span style="color: blue;">new </span><span style="color: #2b91af;">ContactManagerEntityRepository</span>())</span> does. It's called constructor chaining. And it is at that point that the dependency (the ContactManagerEntityRepository) gets injected into the Controller. But now, if you look at the Index Action, you can see that the GetContacts() method call is made against the IContactRepository interface instead of an instance of a concrete implementation of that interface (which is what the ContactEntityManagerRepository is).</p>
<p>If you wanted to swap the EF based data access component out and replace it with the LINQ to SQL version, you would simply have to make one change to the Controller.&nbsp; You would no longer pass in an instance of the ContactManagerEntityRepository class into the chained constructor.&nbsp; You would make that ContactManagerLinqRepository instead:</p>
<pre class="code"><span style="color: blue;">public class </span><span style="color: #2b91af;">ContactController </span>: <span style="color: #2b91af;">Controller </span>{
  <span style="color: blue;">private readonly </span><span style="color: #2b91af;">IContactRepository </span>iRepository;

  <span style="color: blue;">public </span>ContactController() : <span style="color: blue;">this</span>(<span style="color: blue;">new </span><span style="color: #2b91af;"><strong>ContactManagerLinqRepository</strong></span>())
  {}

  <span style="color: blue;">public </span>ContactController(<span style="color: #2b91af;">IContactRepository </span>repository)
  {
    iRepository = repository;
  }

  <span style="color: blue;">public </span><span style="color: #2b91af;">ActionResult </span>Index()
  {
    <span style="color: blue;">return </span>View(iRepository.GetContacts());
  }
}

</pre>
<p>This is a lot better.&nbsp; The Controller is a lot more loosely coupled to the nature of the component.&nbsp; And this is how both the Contact Manager and the Nerd Dinner samples implement DI. Changes can be made quite simply, although if you have a lot of dependencies things can be a little more complicated.&nbsp; You could use Find and Replace to update multiple controllers, so long as you can be sure you don't accidentally alter other files where the Replace operation breaks things.&nbsp; Hmmm... Do you hear a faint creaking sound in the far off distance?&nbsp; Maybe this approach isn't that rock solid after all, and perhaps that's why the approach outlined above is also known rather derogatorily as "Poor Man's Dependency Injection".</p>
