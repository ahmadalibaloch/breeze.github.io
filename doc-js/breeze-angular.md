﻿---
foo: bar
---

<div class="content">
    <div class="field field-name-body field-type-text-with-summary field-label-hidden">
        <div class="field-items">
            <div class="field-item even">
                <h1>Breeze Angular Service - {{page.foo}}</h1>

                <p>Breeze and Angular work well together. They work <em>better</em> together when you configure Breeze to use Angular promises (<code>$q</code>) and Angular's ajax component (<code>$http</code>).</p>

                <p>The <strong>Breeze Angular Service</strong> is a Breeze "bridge" adapter that performs this configuration for you in an "ngNatural" way.</p>

                <p class="note" style="background-color: lightcoral; color:black">Breeze+Angular is great for modern browsers (ECMAScript 5+) that support <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty" target="_blank" style="color: blue"><strong>Object.defineProperty</strong></a>. If your app must run in IE8 or earlier, the Breeze/Angular combination is not for you. You might consider Breeze+Durandal (Knockout).</p>

                <h2>Install it</h2>

                <ol>
                    <li>
                        <p>acquire the <strong><em>breeze.bridge.angular.js</em></strong> JavaScript file in one of the ways described below</p>

                        <blockquote>
                            <p>This <em>breeze.bridge.angular.js</em> used to be a Breeze Labs file named <em>breeze.angular.js</em>. It was moved to Breeze core and renamed in January, 2015.</p>
                        </blockquote>
                    </li>
                    <li><p>load that script on your web page <strong>after</strong> loading breeze itself.</p></li>
                    <li><p>add "breeze.angular" to your application module's list of dependencies</p></li>
                    <li><p>inject the "breeze" service into <em>any</em> application component that runs before invoking a breeze feature; this injection triggers the configuration.</p></li>
                </ol>

                <h3>bower</h3>

                <p>The "breeze.angular" service is included among the adapters in the <strong>breeze-client</strong> bower package.</p>

                <p><code>bower install breeze-client</code></p>

                <p>Now load it in your web page html <strong>after</strong> breeze itself.</p>

                <p><code>&lt;script src="bower_components/breeze-client/adapters/breeze.bridge.angular.js"&gt;&lt;/script&gt;</code></p>

                <h3>npm</h3>

                <p>The "breeze.angular" service is included among the adapters in the <strong>breeze-client</strong> npm package.</p>

                <p class="note">The "breeze-client" npm package becomes available with Breeze release v.1.5.3.</p>

                <p><code>npm install breeze-client</code></p>

                <p>Now load it in your web page html <strong>after</strong> breeze itself.</p>

                <p><code>&lt;script src="node_modules/breeze-client/adapters/breeze.bridge.angular.js"&gt;&lt;/script&gt;</code></p>

                <h3>github source</h3>

                <p>
                    You can download the <a href="https://github.com/Breeze/breeze.js/blob/master/src/breeze.bridge.angular.js">raw JavaScript file from github</a>. Put it wherever you like.
                    Load it in your web page html  <strong>after</strong> breeze itself.
                </p>

                <h3>nuget</h3>

                <p>Visual Studio users can <a href="http://www.nuget.org/packages/Breeze.Angular/" title="breeze.angular on NuGet">install it with NuGet</a>:</p>

                <p><code>Install-Package Breeze.Angular</code></p>

                <p>Now load it in your web page html <strong>after</strong> breeze itself.</p>

                <p><code>&lt;script src="Scripts/breeze.bridge.angular.js"&gt;&lt;/script&gt;</code></p>

                <blockquote>
                    <p>The nuget package depends on <a href="http://www.nuget.org/packages/Breeze.Client/">breeze.client</a> and the <a href="http://www.nuget.org/packages/Breeze.Angular.Directives/">breeze.angular.directives package</a> which provides the "zValidate" validation directive. You may be able to install everything you need for Breeze+Angular client development with this one package.</p>
                </blockquote>

                <h2>Examples</h2>

                <p><strong>Example #1</strong>: Configure when your application boots</p>

                <div><div id="highlighter_344001" class="syntaxhighlighter  javascript"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div><div class="line number4 index3 alt1">4</div><div class="line number5 index4 alt2">5</div><div class="line number6 index5 alt1">6</div><div class="line number7 index6 alt2">7</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="javascript keyword">var</code> <code class="javascript plain">app = angular.module(</code><code class="javascript string">'app'</code><code class="javascript plain">, [</code></div><div class="line number2 index1 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript comments">// ... other dependencies ...</code></div><div class="line number3 index2 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript string">'breeze.angular'</code> <code class="javascript comments">// the breeze service module</code></div><div class="line number4 index3 alt1"><code class="javascript plain">]);</code></div><div class="line number5 index4 alt2">&nbsp;</div><div class="line number6 index5 alt1"><code class="javascript comments">// Ensure that breeze is minimally configured by loading it when the app runs</code></div><div class="line number7 index6 alt2"><code class="javascript plain">app.run([</code><code class="javascript string">'breeze'</code><code class="javascript plain">, </code><code class="javascript keyword">function</code> <code class="javascript plain">(breeze) { }]); </code><code class="javascript comments">// doing nothing at the moment</code></div></div></td></tr></tbody></table></div></div>

                <p><strong>Example #2</strong>: Configure upon your first use of Breeze</p>

                <div><div id="highlighter_391982" class="syntaxhighlighter  javascript"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div><div class="line number4 index3 alt1">4</div><div class="line number5 index4 alt2">5</div><div class="line number6 index5 alt1">6</div><div class="line number7 index6 alt2">7</div><div class="line number8 index7 alt1">8</div><div class="line number9 index8 alt2">9</div><div class="line number10 index9 alt1">10</div><div class="line number11 index10 alt2">11</div><div class="line number12 index11 alt1">12</div><div class="line number13 index12 alt2">13</div><div class="line number14 index13 alt1">14</div><div class="line number15 index14 alt2">15</div><div class="line number16 index15 alt1">16</div><div class="line number17 index16 alt2">17</div><div class="line number18 index17 alt1">18</div><div class="line number19 index18 alt2">19</div><div class="line number20 index19 alt1">20</div><div class="line number21 index20 alt2">21</div><div class="line number22 index21 alt1">22</div><div class="line number23 index22 alt2">23</div><div class="line number24 index23 alt1">24</div><div class="line number25 index24 alt2">25</div><div class="line number26 index25 alt1">26</div><div class="line number27 index26 alt2">27</div><div class="line number28 index27 alt1">28</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="javascript keyword">var</code> <code class="javascript plain">app = angular.module(</code><code class="javascript string">'app'</code><code class="javascript plain">, [</code></div><div class="line number2 index1 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript comments">// ... other dependencies ...</code></div><div class="line number3 index2 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript string">'breeze.angular'</code> <code class="javascript comments">// the breeze service module</code></div><div class="line number4 index3 alt1"><code class="javascript plain">]);</code></div><div class="line number5 index4 alt2">&nbsp;</div><div class="line number6 index5 alt1"><code class="javascript comments">// Any first use of breeze would likely involve the breeze.EntityManager.</code></div><div class="line number7 index6 alt2"><code class="javascript comments">// Apps often combine EntityManager and breeze configuration in a "factory".</code></div><div class="line number8 index7 alt1"><code class="javascript comments">// This 'entityManagerFactory' creates a new EntityManager</code></div><div class="line number9 index8 alt2"><code class="javascript comments">// configured for a specific remote service.</code></div><div class="line number10 index9 alt1"><code class="javascript plain">angular.module(</code><code class="javascript string">'app'</code><code class="javascript plain">)</code></div><div class="line number11 index10 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.factory(</code><code class="javascript string">'entityManagerFactory'</code><code class="javascript plain">, [</code><code class="javascript string">'breeze'</code><code class="javascript plain">, emFactory]);</code></div><div class="line number12 index11 alt1">&nbsp;</div><div class="line number13 index12 alt2"><code class="javascript keyword">function</code> <code class="javascript plain">emFactory(breeze) {</code></div><div class="line number14 index13 alt1"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript comments">// Convert properties between server-side PascalCase and client-side camelCase</code></div><div class="line number15 index14 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript plain">breeze.NamingConvention.camelCase.setAsDefault();</code></div><div class="line number16 index15 alt1">&nbsp;</div><div class="line number17 index16 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript comments">// Identify the endpoint for the remote data service</code></div><div class="line number18 index17 alt1"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript keyword">var</code> <code class="javascript plain">serviceRoot = window.location.protocol + </code><code class="javascript string">'//'</code> <code class="javascript plain">+ window.location.host + </code><code class="javascript string">'/'</code><code class="javascript plain">;</code></div><div class="line number19 index18 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript keyword">var</code> <code class="javascript plain">serviceName = serviceRoot + </code><code class="javascript string">'breeze/breeze'</code><code class="javascript plain">; </code><code class="javascript comments">// breeze Web API controller</code></div><div class="line number20 index19 alt1">&nbsp;</div><div class="line number21 index20 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript comments">// the "factory" services exposes two members</code></div><div class="line number22 index21 alt1"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript keyword">var</code> <code class="javascript plain">factory = {</code></div><div class="line number23 index22 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">newManager: </code><code class="javascript keyword">function</code><code class="javascript plain">() {</code><code class="javascript keyword">return</code> <code class="javascript keyword">new</code> <code class="javascript plain">breeze.EntityManager(serviceName);},</code></div><div class="line number24 index23 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">serviceName: serviceName</code></div><div class="line number25 index24 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript plain">};</code></div><div class="line number26 index25 alt1">&nbsp;</div><div class="line number27 index26 alt2"><code class="javascript spaces">&nbsp;&nbsp;</code><code class="javascript keyword">return</code> <code class="javascript plain">factory;</code></div><div class="line number28 index27 alt1"><code class="javascript plain">}</code></div></div></td></tr></tbody></table></div></div>

                <p>The Breeze Angular Service is not clairvoyant. It can't configure Breeze for everything your app requires. The second example illustrates configuration of the <code>NamingConvention</code> and the remote service endpoint (the <code>serviceName</code>), both specific to your application.</p>

                <h2>The Breeze service instance</h2>

                <p>The 'breeze' service that Angular injects is Breeze itself, identical to <code>window.breeze</code>. Whether you use that service object or refer to the global <code>breeze</code> object is a matter of style.</p>

                <p>The "Breeze Angular Service" simply configures Breeze to use</p>

                <ul>
                    <li>Angular for data binding </li>
                    <li>the <code>$q</code> service for promises </li>
                    <li>the <code>$http</code> service for ajax calls </li>
                </ul>

                <p>The balance of this documentation provides more details about promises and the ajax service.</p>

                <h2>Promises</h2>

                <p>A <strong>promise</strong> is a pledge to tell you when an asynchronous activity completes.</p>

                <p>Breeze and Angular rely on promises to manage chaining of asynchronous method calls such as a sequence of data queries.</p>

                <p>Every Breeze async method returns a <strong><em>promise object</em></strong>. Initially the asynchronous activity is incomplete and the promise object is "unfullfilled". Your code continues without knowing the outcome of that activity. The promise object has a <code>then()</code> method. You supply success and failure callbacks as parameters to the <code>then()</code>. When the asynchronous activity completes, the promise is "fullfilled" and it invokes either your success or your failure callback as appropriate.</p>

                <p><a href="https://github.com/kriskowal/uncommonjs/blob/master/promises/specification.md" title="&quot;Thenable Promises&quot;">Read more about "Thenable Promises</a>" from the author of the Q.js library, <a href="https://github.com/kriskowal" title="Kris Kowal">Kris Kowal</a>. The Angular <code>$q</code> implementation adheres to his description in all essential respects.</p>

                <h3>Breeze promises</h3>

                <p>Out of the box, a Breeze asynchronous method returns a <a href="http://documentup.com/kriskowal/q/" target="_blank"><strong>Q.js</strong> promise</a>, not an AngularJS <a href="http://docs.angularjs.org/api/ng.$q" target="_blank"><strong><code>$q</code></strong> promise</a>. Breeze also assumes that you included the Q.js library in your client stack.</p>

                <p>While the Q.js default makes good sense in other environments, it is not Angular friendly. First you have to load the Q library. Then you'll find that you often have to convert a Q promise to a <code>$q</code> promise because many Angular components don't understand a Q promise. Because the Angular dirty-checking <a href="http://docs.angularjs.org/api/ng/type/$rootScope.Scope#$digest">"Digest" cycle</a> knows nothing of Q, you'll probably have to call <a href="http://docs.angularjs.org/api/ng/type/$rootScope.Scope#$apply"><code>$scope.$apply</code></a>. Finally, it's extremely difficult to test with <code>ng-mocks</code> when you have a mix of <code>$q</code> and Q promises.</p>

                <p>Angular developers should switch to <code>$q</code> promises and this Breeze Angular Service does that for you automatically.</p>

                <h3><code>$q</code> usage</h3>

                <p>There's nothing to it. Breeze async methods now return Angular <code>$q</code> promises. Append promise callbacks to those promises per the <code>$q</code> API.</p>

                <div><div id="highlighter_273591" class="syntaxhighlighter  javascript"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="javascript keyword">var</code> <code class="javascript plain">promise = entityManager</code></div><div class="line number2 index1 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.executeQuery(query)</code></div><div class="line number3 index2 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.then(successCallback, failCallback); </code><code class="javascript comments">// not preferred; see next.</code></div></div></td></tr></tbody></table></div></div>

                <h3>exceptions</h3>

                <p>What if one of the callbacks throws an exception? Per <a href="https://github.com/kriskowal/uncommonjs/blob/master/promises/specification.md" title="&quot;Thenable Promises&quot;">the specification</a>, if either the <code>successCallback</code> or <code>failCallback</code> throws an exception, the promise returned from <code>then(...)</code> is rejected. Don't expect a failed <code>successCallback</code> to propagate its error to the sibling <code>failCallback</code>.</p>

                <p>Because the <code>successCallback</code> is often fragile, especially in tests, we often move the <code>failCallback</code> to a separate <code>then(null, failCallback)</code> so that it can catch failures either of the original promise or of the "success path" promise.</p>

                <blockquote>
                    <p>The <code>$q</code> promise sports a "sugar" method, <code>.catch(failCallback)</code>, which is the same as <code>.then(null, failCallback)</code>.</p>
                </blockquote>

                <p>You may also need cleanup logic that should run whether the original promise succeeds or fails.</p>

                <blockquote>
                    <p>While you could append <code>.then(wrapUp, wrapUp)</code>, we prefer another bit of sugar,  <code>.finally(wrapUp)</code>.</p>
                </blockquote>

                <p>Putting these thoughts together we might write something like this:</p>

                <div><div id="highlighter_937121" class="syntaxhighlighter  javascript"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div><div class="line number4 index3 alt1">4</div><div class="line number5 index4 alt2">5</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="javascript keyword">var</code> <code class="javascript plain">promise = entityManager</code></div><div class="line number2 index1 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.executeQuery(query)</code></div><div class="line number3 index2 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.then(successCallback)</code></div><div class="line number4 index3 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.</code><code class="javascript keyword">catch</code><code class="javascript plain">(failCallback) </code></div><div class="line number5 index4 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">.finally(wrapUp);</code></div></div></td></tr></tbody></table></div></div>

                <p>We encourage you to review the <a href="http://docs.angularjs.org/api/ng.$q" target="_blank"><strong>$q</strong> promises documentation</a> for details.</p>

                <h2>AJAX</h2>

                <p>The Breeze <code>EntityManager</code> makes HTTP calls to a remote server via an "ajax" adapter. While Breeze ships with both a 'jQuery' and an 'angular' ajax adapter, it defaults to the 'jQuery' adapter which wraps <code>jquery.ajax</code>. This Breeze Angular Service re-configures breeze to use the 'angular' adapter which wraps <code>$http</code>, ensuring that Breeze receives the specific <code>$http</code> service instance that Angular injects into your app module.</p>

                <p>Speaking of service instances ...</p>

                <h2>Multiple <code>$q</code> and <code>$http</code> instances</h2>

                <p>There is a nuance you may discover in extraordinary circumstances: Angular creates a new <code>$q</code> and a new <code>$http</code> <em>for each application module</em>.</p>

                <p>Rare is the application that has multiple app modules. But if you did have multiple app modules, each would have its own <code>$q</code> and <code>$http</code> instance.</p>

                <p>Breeze expects exactly one promise and ajax implementation across the entire application. That <em>might</em> become a problem if you toggled between multiple app modules. You could workaround it by switching the Breeze promise  and ajax implementations every time you switch app modules. The specifics of this technique are beyond the scope of this topic.</p>

                <p>You're more likely to become aware of multiple <code>$q</code> and <code>$http</code> instances during testing. In fact, you can <em>count on getting a new instance</em> for each and every test (known as a "spec" in Jasmine).</p>

                <p>Fortunately, you get a new instance of the app module too. So when your app module and services load under test, they create a fresh instance of the Breeze Angular service at the same time ... and that new instance will configure Breeze with the current <code>$q</code> and <code>$http</code> services for each executing test (or "spec").</p>

                <p>Here's an example of a Jasmine "beforeEach" test setup:</p>

                <div><div id="highlighter_322367" class="syntaxhighlighter  javascript"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="gutter"><div class="line number1 index0 alt2">1</div><div class="line number2 index1 alt1">2</div><div class="line number3 index2 alt2">3</div><div class="line number4 index3 alt1">4</div></td><td class="code"><div class="container"><div class="line number1 index0 alt2"><code class="javascript plain">beforeEach(</code><code class="javascript keyword">function</code> <code class="javascript plain">() {</code></div><div class="line number2 index1 alt1"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">module(</code><code class="javascript string">'app'</code><code class="javascript plain">); </code><code class="javascript comments">// new instance of the 'app' module</code></div><div class="line number3 index2 alt2"><code class="javascript spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="javascript plain">inject(</code><code class="javascript keyword">function</code><code class="javascript plain">(breeze){ }); </code><code class="javascript comments">// just to be sure.</code></div><div class="line number4 index3 alt1"><code class="javascript plain">})</code></div></div></td></tr></tbody></table></div></div>
            </div>
        </div>
    </div>
</div>