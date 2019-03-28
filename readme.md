
A guide to enable MULTISITE in wordpress

1. go to the hosting - open wp_config.php - add following line and save.
//mulsite

define( 'WP_ALLOW_MULTISITE', true );

2. Goto the wp-admin- tools- network setup-

  Two types
    1.Subdomains — a domain-based network in which on-demand sites use subdomains
      eg. abc.com/new-site/
    2.Subdirectories — a path-based network in which on-demand sites use paths
      e.g based on directories inside the main setup

choose any one of it.

// note you will see this option for new setup
//for existing setup you will get subdomain by default

 enable any one of it.
 
3. Copy the generated code in respective wp-config.php and .htaccess file
//sample attached

4. Now you will see the network admin on top bar - goto network admin- enable plugins as required for sites

5. Also you can create any number of sites now on.

Q & A
1. what happens to original site?
  it is part of the network now.

2. What is network enable plugins?
  only plugins that will be network active will be added and activated in new site

3. how is db maintained?
  each subsite has unique id, db tables are re-created for each site with site id

4. how to access db tables of one subsite from another?
  you have make switch to subsite using site id
  
  switch_to_blog( $id );

 //do your compution and restore
  
  restore_current_blog();

5. how to convert from Subdirectories to subdomain in wordpress?
change this in wp-cofig and update htaccess accordingly

define('SUBDOMAIN_INSTALL', true);

//warning backup before doing this
