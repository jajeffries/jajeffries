---
title: 'Naming boolean methods'
date: Tue, 07 Mar 2017 08:51:31 +0000
draft: false
tags: []
---

I've been thinking a bit over the last few days about something I've seen quite a lot in a code base I'm working on: method names that exactly describe the contents of a method returning a boolean. For example,

```csharp
bool IsUkCultureAndIsNotPublished(Page page) { return page.Culture == "en-GB" && !page.IsPublished; }
```

Forgetting about all the other things wrong with this code it introduces some duplication between the name and what the method does. Next let's look at the place it's used.

```csharp
var pages = GetPages();
pages.Where(IsUkCultureAndIsNotPublished).ToList().ForEach(Publish);
```

What if we need to add another condition? Do we add it inside our method and change the name?

```csharp
bool IsUkCultureAndIsNotPublishedAndIsValid(Page page) {
    return page.Culture == "en-GB" && !page.IsPublished && page.IsValid;
}
```

That seems like at some point someone won't remember to change the name. Maybe we should add it outside the method and wrap that in another method?

```csharp
bool IsUkCultureAndIsNotPublishedAndIsValid(Page page) {
    return IsUkCultureAndIsNotPublished(page) && page.IsValid;
}
...

var pages = GetPages();
pages.Where(IsUkCultureAndIsNotPublishedAndIsValid).ToList().ForEach(Publish);
```

That seems a bit confusing too and now we've introduced more duplication. The name of our IsUkCultureAndIsNotPublished method doesn't tell us the intent. It breaks encapsulation because it's telling us the internals of the method. I'd suggest that a better name might be something like IsReadyToPublish. Let's have a look at our calling code now.

```csharp
var pages = GetPages()
pages.Where(IsReadyToPublish).ToList().ForEach(Publish);
```

Now we can see why we are publishing the pages. Instead of having some pages that are Uk culture and not published, we have pages that are ready to publish. Describing the intent of the method allows us to have more readable code that you're more likely to understand when you come to read your code in 6 months time and reduces the number of places you need to update if your requirements change.