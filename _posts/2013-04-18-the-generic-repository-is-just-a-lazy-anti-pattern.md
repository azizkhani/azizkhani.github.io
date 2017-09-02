---
layout: post
title: "The generic repository is just a lazy anti-pattern"
comments: true
---
<p class="intro">A generic repository is often used with the entity framework to speed up the process of creating a data layer. In most cases this is a generalization too far and it can be a trap for lazy developers.</p>
<p>A generic repository often looks something like the code below. It defines generic methods for the most common types of data operation, such as updating, fetching and deleting. It&rsquo;s appealing to developers because it&rsquo;s simple, flexible and allows you to crank out a large domain model without having to write a lot of code.</p>
<div class="code_container">
<div class="code_area">
<pre class="java">public interface IRepository
{
    IEnumerable GetAll();
    IEnumerable Find(Expression&gt; query);
    T GetByID(int id);
    void Add(T item);
    void Update(T item);
    void Delete(T item);
}</pre>
</div>
</div>
<p>The problem is that this is not a neat and convenient abstraction, but rather a time-saving short-cut that can undermine the coherence of a solution in a number of respects.</p>
<h2>It&rsquo;s a leaky abstraction</h2>
<p><a href="http://martinfowler.com/eaaCatalog/repository.html" target="_blank">Martin Fowler</a> defines a repository as an &ldquo;object that mediates between the domain and data mapping layers&rdquo;. The objective is to isolate domain objects from details of the data access code.</p>
<p>However, the generic repository can allow developers to wrap the underlying data access technology such as Entity Framework classes. This allows a direct dependency from the data access technology to leak out into the application logic.</p>
<p>A repository should abstract the entire data access layer and enforce the concealment of details such as the database engine or data access technology. This generic implementation&nbsp;does not necessarily isolate anything &ndash; it&rsquo;s just adding a pointless and leaking abstraction with no guaranteed benefits.</p>
<h2>It&rsquo;s too much of a generalization</h2>
<p>Most repositories need &ldquo;Save&rdquo; and &ldquo;Delete&rdquo; methods&hellip; well, actually, <em>do they</em>? One objection to the generic repository is that it&rsquo;s just plain <em>lazy</em> as the developer has not taken the time to consider <em>how</em> any consuming classes will use it. For example, are there any specialized fetch methods you need that may support, say, pagination? Will the repository specialize in reading or updating the model?</p>
<p>Very few real-world domain models can be addressed by the same set of methods. You should consider <em>how</em> you want data to be used. Once you start trying to serve more specialized business requirements then the generic repository quickly starts to look inadequate.</p>
<h2>It doesn&rsquo;t define a meaningful contract</h2>
<p>The repository should represent a <em>contract</em> between the domain objects and a data store. It defines the kinds of operations that a data store is expected to service. A weakness of the generic repository is that it defines this contract so widely that it becomes almost meaningless.</p>
<p>The first line of code below illustrates the kind of search method that is often found in generic repositories. It provides a lot of flexibility over how you might query data, but it&rsquo;s impossible to tell what form of contract this represents. It could be asking the data store to return pretty much <em>anything</em>.</p>
<div class="code_area">
<pre class="csharp">    
IQueryable Find(object query);
    IQueryable FindCustomerByName(string name);
</pre>
</div>
<p>The second line represents something far more concrete. It clearly defines the relationship between domain objects and data store. Apart from the certainty of the contract, it provides a far more <em>readable</em> implementation.</p>
<h2>A generic repository does have a place&hellip; just not on the frontline</h2>
<p>Nobody likes to repeat themselves, but a generic repository interface is an over generalization. That said, there&rsquo;s nothing to stop you from using a generic repository class as part of a more specific repository implementation. This will help you to derive the re-use benefits of a generic repository whilst still providing a strongly-defined contract.</p>
<p>The code below shows a simple example where a generic <span class="code">Repository&lt;T&gt;</span> class marked for internal access is used within a public-facing repository implementation. This composition approach cuts down on the amount of code you have to write whilst still providing a meaningful public-facing contract.</p>
<div class="code_container">
<div class="code_area">
<pre class="csharp">public class CustomerRepository
{
    private Repository internalRepository;

    public IEnumerable FindCustomerByName(string input)
    {
        return internalRepository.FindBy(c =&gt; c.Name == input);
    }
}</pre>
</div>
</div>
<p>A generic repository does have a place, but as a <em>helper</em> rather than a contract. The trick is not to expose a generic interface but achieve re-use through composition.</p>
<p>thanks mohsen salehi for share this post</p>
<p>ref:http://www.ben-morris.com/why-the-generic-repository-is-just-a-lazy-anti-pattern</p>
