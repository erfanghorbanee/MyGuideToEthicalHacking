# Windows PE File Format

## DOS Header + Stub

![c9b1b17aeead0f7e13cbdf2cf923cd2d.png](../../_resources/c9b1b17aeead0f7e13cbdf2cf923cd2d.png)

This is useless to be honest, but it can be manipulated. in the following picture, blue area can be manipulated but it's not executable because it's not defined as it. 

![9a256c2f51d86573d2a45db263b9e266.png](../../_resources/9a256c2f51d86573d2a45db263b9e266.png)

We can exploit the offset to real header and create extra space for our content! notice the gap in the picture between dos header and PE header.

![ce66f6efdbe6fe4724a347113086822c.png](../../_resources/ce66f6efdbe6fe4724a347113086822c.png)

## PE Header

![7fb96d94525c02f015ce47c87e5c8956.png](../../_resources/7fb96d94525c02f015ce47c87e5c8956.png)

## Optional Header

![c14b827dc6ebc3a901d24c312ccf5fbb.png](../../_resources/c14b827dc6ebc3a901d24c312ccf5fbb.png)

## Section Table and Sections

![4b3630bd3f5d9263ec0552e42b972af8.png](../../_resources/4b3630bd3f5d9263ec0552e42b972af8.png)

we can exploit it:
![73c13e2b451e1b3322b28ec3eb5a263a.png](../../_resources/73c13e2b451e1b3322b28ec3eb5a263a.png)

you can even add your own section!
![8e735058b44464215571ffc4c40a89bc.png](../../_resources/8e735058b44464215571ffc4c40a89bc.png)

## How programs are loaded

![997cbf094a71c37aedf07534edb48a0e.png](../../_resources/997cbf094a71c37aedf07534edb48a0e.png)