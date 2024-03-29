my-movies
---------
The aim behind this application is to be an unoptimized reference implementation for "a social benchmark".

Proper benchmarking is all about showing how a database can perform given a workload as close to realistic as possible.  For example TPC-C "is centered around the principal activities (transactions) of an order-entry environment.  These transactions include entering and delivering orders, recording payments, checking the status of orders, and monitoring the level of stock at the warehouses." (source: http://www.tpc.org/tpcc/).

The problem is, not everyone building web-applications is managing warehouses.  More people are building social applications.

Deploying
=========

    # first time
    bundle install
    cap cowboy deploy:setup
    # setup Host entries in ~/.ssh/config

    # every time
    cap cowboy deploy


Prior Art/Examples
==================

The best-known prior art is the Dell DVD store demo (http://linux.dell.com/dvdstore/).  The aim of the benchmark is to simulate a typical online e-commerce site with implementations provided for Microsoft SQL Server, Oracle and MySQL - and applications written in .NET, PHP and Java.  This benchmark is slightly different, in that it aims to test "full stack performance".  Alternative implementations written in other scripting languages using NoSQL databases are encouraged!

A perhaps lesser known example of full-stack is the ReserveWithUsApp written to teach Database Tuning principles <http://code.google.com/p/databasetuning-cases/>.  This goals behind ReserveWithUs are very compatible with that of this project.  The author of this project confess to not knowing of the existence of ReserveWithUs until very late in development.  The main suspected difference with ReserveWithUs does not include social features.

I have an optimization - will you accept my patch?
==================================================

The code is intentionally *not optimized*.  It has some huge performance problems - and probably security vulnerabilities!  We want the reference implementation to have educational benefit, so that users can learn to instrument before optimizing.

We will happily accept patches that improve usability of the source code, or add more social features (such as activity feeds, user walls etc).

We will also happily link to alternative implementations/branches that have been optimized.
