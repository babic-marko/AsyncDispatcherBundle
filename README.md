AsyncDispatcherBundle
=====================

[![SensioLabsInsight](https://insight.sensiolabs.com/projects/ac7bf46c-aa2a-4100-bcf0-c3bad08cc713/small.png)](https://insight.sensiolabs.com/projects/ac7bf46c-aa2a-4100-bcf0-c3bad08cc713)
[![knpbundles.com](http://knpbundles.com/BranchBit/AsyncDispatcherBundle/badge-short)](http://knpbundles.com/BranchBit/AsyncDispatcherBundle)


[![Build Status](https://travis-ci.org/BranchBit/AsyncDispatcherBundle.svg?branch=master)](https://travis-ci.org/BranchBit/AsyncDispatcherBundle)
[![Coverage Status](https://coveralls.io/repos/BranchBit/AsyncDispatcherBundle/badge.png?branch=master)](https://coveralls.io/r/BranchBit/AsyncDispatcherBundle?branch=master)

[![Latest Stable Version](https://poser.pugx.org/bbit/async-dispatcher-bundle/v/stable.png)](https://packagist.org/packages/bbit/async-dispatcher-bundle)
[![Total Downloads](https://poser.pugx.org/bbit/async-dispatcher-bundle/downloads.png)](https://packagist.org/packages/bbit/async-dispatcher-bundle)


AsyncDispatcherBundle is a simple bundle which provides you with an async event dispatcher, which will store events untill kernel.terminate, and then fire them using the regular event dispatcher.


### Step 1: Download BBITAsyncDispatcherBundle using composer

Add BBITAsyncDispatcherBundle in your composer.json: (use the latest stable, NOT dev-master)

```js
{
    "require": {
        "bbit/async-dispatcher-bundle": "2.5.0",
    }
}
```

Now tell composer to download the bundle by running the command:

``` bash
$ php composer.phar update bbit/async-dispatcher-bundle
```

Composer will install the bundle to your project's `vendor/BBIT` directory.

### Step 2: Enable the bundle

Enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new BBIT\AsyncDispatcherBundle\BBITAsyncDispatcherBundle(),
    );
}
```


### Usage:

``` php
$dispatcher = $this->container->get('bbit_async_dispatcher.dispatcher'); // get dispatcher service
$dispatcher->addAsyncEvent(new CustomEvent($entity), 'name_of_the.event');
```






### More BBIT Bundles: 
>[**SqsCommandQueueBundle**][sqsbundle] is a simple bundle, wich you can use, to queue commands on amazon SQS. These can then be processed asynchronously by one or more workers.  [![Latest Stable Version](https://poser.pugx.org/bbit/sqs-command-queue-bundle/v/stable.png)](https://packagist.org/packages/bbit/sqs-command-queue-bundle)

[sqsbundle]: <http://branchbit.github.io/SqsCommandQueueBundle/>
