Byte Chameleon [![Build Status](https://travis-ci.org/renatomartinsti/byte-chameleon.svg?branch=master)](https://travis-ci.org/renatomartinsti/byte-chameleon) [![Quality Gate](https://sonarcloud.io/api/badges/gate?key=br.com.remartins:byte-chameleon)](https://sonarcloud.io/dashboard/index/br.com.remartins:byte-chameleon)
============

JavaAgent Replace Methods with Javassist


How To
------

Add to params

```
-javaagent:byte-chameleon.jar=agent.xml
```
where <b>agent.xml</b> is

```
<byte-chameleon>
  <classes>
    <classe>
      <nome>br.com.agent.Processamento</nome>
      <metodos>
        <metodo tipo="replace">
          <nome>processar</nome>
          <parametros>java.lang.String</parametros>
          <codigo>System.out.println("Sou o novissimo processador " + $1);</codigo>
        </metodo>
      </metodos>
    </classe>
    <classe>
      <nome>br.com.agent.Processamento</nome>
      <metodos>
          <metodo tipo="before">
          <nome>processar</nome>
          <parametros>java.lang.String</parametros>
          <codigo>System.out.println("Printer before !!!");</codigo>
        </metodo>
      </metodos>
    </classe>     
  </classes>	
</byte-chameleon>  
```
