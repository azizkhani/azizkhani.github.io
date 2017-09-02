---
layout: post
title: " Reusable components in AngularJS"
comments: true
---
<pre class="brush: js;">angular.module('components', []).directive('category', function () {
return {
    restrict: 'E',
    scope: {},
    templateUrl: '/Scripts/app/partials/<strong>CategoryComponent.html</strong>',
    controller: function ($scope, $http, $attrs) {
        $http({
            url: "api/FeaturedProducts/" + <strong>$attrs.catName</strong>,
            method: "get"
        }).success(function (data, status, headers, config) {
            $scope.Cat = data;
        }).error(function (data, status, headers, config) {
            $scope.data = data;
            $scope.status = status;
        });

    }
}
});</pre>
<pre class="lang-js prettyprint prettyprinted"><br /><strong>CategoryComponent.html</strong></pre>
<pre class="brush: xml;">&lt;a href="#/Categories/{{Cat.CategoryName}}"&gt;
    &lt;h4&gt;<strong>{{Cat.CategoryName}}</strong>&lt;/h4&gt;
&lt;/a&gt;
&lt;div ng-switch on="status"&gt;
    &lt;div <strong>ng-switch-when="500"</strong> class="alert alert-error"&gt;
        {{status}}
        {{data}}
    &lt;/div&gt;
    &lt;div ng-switch-default&gt;
        &lt;ul class="unstyled columns"&gt;
            &lt;li class="pin" <strong>ng-repeat="p in Cat.Products"</strong>&gt;
                &lt;a href="#/reviews/{{p.UPC}}"&gt;
                    &lt;h5&gt;{{p.ProductName}}&lt;/h5&gt;
                    &lt;img src="{{p.ImageUrl}}"&gt;
                &lt;/a&gt;
            &lt;/li&gt;
        &lt;/ul&gt;
    &lt;/div&gt;
&lt;/div&gt;<br /><br /><br /><strong>usage</strong></pre>
<pre class="brush: xml;">&lt;ul class="unstyled"&gt;
    &lt;li&gt;
    &lt;<strong>category</strong> <strong>cat-name</strong>="Ultrabooks"&gt;&lt;/category&gt;
    &lt;/li&gt;
    &lt;li&gt;
    &lt;category cat-name="Tablets"&gt;&lt;/category&gt;
    &lt;/li&gt;
    &lt;li&gt;
    &lt;category cat-name="Laptops"&gt;&lt;/category&gt;
    &lt;/li&gt;
    &lt;li&gt;
    &lt;category cat-name="Digital SLR Cameras"&gt;&lt;/category&gt;
    &lt;/li&gt;<br />&lt;/ul&gt;</pre>
