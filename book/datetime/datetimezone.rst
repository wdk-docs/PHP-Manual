DateTimeZone类
===============

.. php:class:: DateTimeZone


   .. php:const:: AFRICA
   
      1
      
   .. php:const:: AMERICA
   
      2
   
   .. php:const:: ANTARCTICA
   
      4
    
   .. php:const:: ARCTIC
   
      8
    
   .. php:const:: ASIA
   
      16
    
   .. php:const:: ATLANTIC
   
      32
    
   .. php:const:: AUSTRALIA
   
      64
    
   .. php:const:: EUROPE
   
      128
    
   .. php:const:: INDIAN
   
      256
    
   .. php:const:: PACIFIC
   
      512
    
   .. php:const:: UTC
   
      1024
    
   .. php:const:: ALL
   
      2047
    
   .. php:const:: ALL_WITH_BC
   
      4095
    
   .. php:const:: PER_COUNTRY
   
      4096
    

   .. php:method:: __construct ( string $timezone )
   
   .. php:method:: getLocation ( void )
   
   .. php:method:: getName ( void )
   
   .. php:method:: getOffset ( DateTime $datetime )
   
   .. php:method:: getTransitions ([ int $timestamp_begin [, int $timestamp_end ]] )
   
   .. php:method:: listAbbreviations ( void )
   
   .. php:method:: listIdentifiers ([ int $what = DateTimeZone::ALL [, string $country = NULL ]] )
