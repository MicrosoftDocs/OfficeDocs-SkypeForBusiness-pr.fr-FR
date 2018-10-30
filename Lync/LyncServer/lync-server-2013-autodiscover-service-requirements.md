---
title: "Lync Server 2013 : Conf. requise pour le service de découverte automatique"
TOCTitle: Configuration requise pour le service de découverte automatique
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690012(v=OCS.15)
ms:contentKeyID: 49296201
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour le service de découverte automatique pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-25_

Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur le directeur et le pool de serveurs frontaux, et une fois publié dans le DNS, peut être utilisé par les appareils mobiles qui exécutent Lync Mobile pour rechercher des services de mobilité. Pour que les appareils mobiles qui exécutent Lync Mobile puissent tirer parti de la découverte automatique, vous devez modifier les listes des autres noms de sujet des certificats sur chaque directeur et serveur frontal qui exécute le service de découverte automatique. En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.

Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, reportez-vous à [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) dans Planification de la mobilité.

La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses repose sur votre choix de publier le service de découverte automatique sur le port 80 ou sur le port 443 :

  - **Publication sur le port 80** Aucune modification de certificat n’est requise si la requête initiale adressée au service de découverte automatique a lieu via le port 80. Cela est dû au fait que les appareils mobiles qui exécutent Lync accèdent au proxy inverse sur le port 80 en externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne. Pour plus d’informations, consultez la section « Processus de découverte automatique initiale à l’aide du port 80 » dans la suite de cette rubrique.

  - **Publication sur le port 443** La liste des autres noms de sujet sur les certificats utilisés par la règle de publication des services web externes doit contenir une entrée *lyncdiscover.\<sipdomain\>* pour chaque domaine SIP situé au sein de votre organisation.

La réémission de certificats à l’aide d’une autorité de certification interne constitue généralement un processus simple, mais pour les certificats publics utilisés dans la règle de publication des services web, l’ajout de plusieurs entrées d’autres noms de sujet peut s’avérer onéreux. Pour remédier à ce problème, nous recommandons la connexion de découverte automatique initiale via le port 80, laquelle est ensuite redirigée vers le port 8080 sur le directeur ou le serveur frontal.

Par exemple, supposons qu’un client mobile exécutant Lync Mobile soit configuré afin de se connecter à Lync Server 2013 à l’aide de la fonctionnalité de découverte automatique qui utilise le protocole HTTP pour la requête initiale.

## Processus de découverte automatique initiale pour les appareils mobiles à l’aide du port 80

1.  L’appareil mobile qui exécute Lync Mobile recherche dans lyncdiscover.contoso.com, à l’aide du DNS, un emplacement auquel il existe un enregistrement A.

2.  Le DNS externe renvoie l’adresse IP des services web externes au client.

3.  L’appareil mobile qui exécute Lync Mobile envoie la requête http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com au proxy inverse.

4.  La règle de publication web établit un pont pour la requête entre le port 80 en externe et le port 8080 en interne, puis l’achemine vers un directeur ou un serveur frontal.
    
    Étant donné qu’il s’agit d’une requête HTTP et non HTTPS, aucune modification n’est requise dans le certificat stipulé dans la règle de publication des services web externes afin de prendre en charge le service de découverte automatique.

5.  Le service de découverte automatique renvoie les URL des services web externes (au format HTTPS).

6.  L’appareil mobile qui exécute Lync Mobile peut alors se reconnecter au proxy inverse sur le port 443 et être redirigé via 4443 vers le service de mobilité qui s’exécute sur le pool d’accueil de l’utilisateur.
    
    Étant donné que la requête HTTPS concerne l’URL des services web externes par rapport à l’URL du service de découverte automatique, elle réussit car le certificat doit déjà contenir les entrées des autres noms de sujet pour les noms de domaine complets (FQDN) des services web externes.
    
    Dans ce scénario, aucune modification de certificat n’est requise pour prendre en charge la mobilité.
    
    > [!NOTE]  
    > Si le serveur web cible possède un certificat qui ne dispose pas d’une adresse correspondant à lyncdiscover.contoso.com en tant que valeur de la liste des autres noms de sujet :<br />
    a. Le serveur web répond par un « Bonjour de serveur », sans certificat.<br />
    b. L’appareil mobile qui exécute Lync Mobile met immédiatement fin à la session.<br />
    Si le serveur web cible possède un certificat qui comprend lyncdiscover.contoso.com comme valeur de la liste des autres noms de sujet :<br />
    a. Le serveur web répond par un « Bonjour de serveur » et un certificat.<br />
    b. L’appareil mobile qui exécute Lync Mobile valide le certificat et établit la liaison.

Pour prendre en charge une connexion initiale au service de découverte automatique utilisant le port 80 sur votre serveur proxy inverse, vous pouvez créer une règle de publication http similaire à cet exemple pour une règle de publication web de proxy inverse Forefront Threat Management Gateway 2010 :

1.  Créez une règle de publication web (par exemple, **Découverte automatique Lync Server (HTTP)** ).

2.  Dans **Nom public** , entrez lyncdiscover.contoso.com.

3.  Sous l’onglet **Pontage** , sélectionnez uniquement l’option permettant d’établir un pont entre le port 80 et le port 8080 pour les requêtes.

4.  Sous l’onglet **Authentification** , sélectionnez **Aucune authentification** et **Le client ne peut pas s’authentifier directement** .

5.  Validez les modifications, puis déplacez la règle au début de la liste des règles Lync (première position dans l’ordre de traitement).

## Mobilité pour le déploiement dans un domaine distinct

Un espace d’adressage SIP, également appelé *domaine distinct* ou *déploiement hybride* est une configuration dans laquelle les utilisateurs sont déployés sur site et dans un environnement en ligne. L’objectif est de permettre à un utilisateur, quel que soit l’emplacement de son serveur central (sur site ou en ligne), de se connecter au déploiement et d’être redirigé vers l’emplacement de son serveur central. La fonctionnalité de découverte automatique de Microsoft Lync Server 2013 est alors utilisée pour rediriger l’utilisateur en ligne vers la topologie en ligne. Pour cela, l’URL de la découverte automatique doit être configurée à l’aide de Lync Server Management Shell et des applets de commande **Get-CsHostingProvider** et **Set-CsHostingProvider** .

Vous devrez recueillir et enregistrer les attributs déployés suivants :

  - Depuis Lync Server Management Shell, tapez
    
        Get-CsHostingProvider

  - Dans les résultats, recherchez le fournisseur en ligne avec l’attribut **ProxyFQDN** . Par exemple, sipfed.online.lync.com.

  - Enregistrez la valeur de l’attribut ProxyFQDN.

  - Activez la fédération dans le Panneau de configuration Lync Server sur site, en autorisant la fédération avec le fournisseur en ligne.

  - Activez la fédération pour le fournisseur en ligne. Par défaut, tous les utilisateurs en ligne sont activés pour la fédération de domaine et peuvent communiquer avec tous les domaines.

  - Si vous envisagez de définir les domaines bloqués et autorisés, déterminez les domaines que vous autoriserez et bloquerez de façon explicite.

  - Pour la fédération en ligne, vous devez planifier les exceptions de pare-feu, les certificats et les enregistrements d’hôte DNS (A ou AAAA, avec IPv6). En outre, vous devez configurer les stratégies de fédération. Pour plus d’informations, reportez-vous à [Planification pour la fédération de Lync Server et Office Communications Server](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

