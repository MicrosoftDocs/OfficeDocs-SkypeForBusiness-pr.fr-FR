---
title: 'Lync Server 2013 : Certificats requis pour l’accès des utilisateurs externes'
TOCTitle: Certificats requis pour l’accès des utilisateurs externes
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398920(v=OCS.15)
ms:contentKeyID: 49298948
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

logiciels de communicationMicrosoft Lync Server 2013 prend en charge l’utilisation d’un certificat public unique pour les interfaces externes Edge d’accès et de conférence Web, et pour le service d’authentification A/V. L’interface interne Edge utilise généralement un certificat privé émis par une autorité de certification interne, mais peut également utiliser un certificat public s’il provient d’une autorité de certification approuvée. Le proxy inverse de votre déploiement utilise un certificat public et chiffre les communications du proxy inverse vers les clients et les serveurs internes en utilisant HTTP (c’est-à-dire, TLS sur HTTP).

Le certificat public utilisé pour les interfaces externes Edge d’accès et de conférence web et pour le service d’authentification A/V doit remplir les conditions suivantes :

  - Le certificat doit être émis par une autorité de certification publique approuvée qui prend en charge les autres noms de sujet. Pour plus d’informations, reportez-vous à l’article 929395 de la base de connaissances Microsoft, « Partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).

  - Si vous comptez utiliser le certificat dans un pool de serveurs Edge, vous devez le créer de manière à pouvoir l’exporter, en utilisant le même certificat sur chaque serveur Edge du pool. Les exigences de clé privée exportable concernent le service d’authentification A/V, qui doit utiliser la même clé privée sur tous les serveurs Edge du pool.

  - Si vous voulez optimiser la durée active de vos services Audio/Vidéo, consultez les conditions préalables requises du certificat pour l’implémentation d’un certificat service Edge A/V découplé (c’est-à-dire un certificat service Edge A/V différent des certificats Edge externes destinés à d’autres usages). Pour plus d’informations, reportez-vous aux rubriques [Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Planification des certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) et [Préparation de certificats AV et OAuth dans Lync Server 2013 à l’aide du paramètre -Roll dans l’applet de commande Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate).

  - Le nom de sujet du certificat est le nom de domaine complet de l’interface externe du service Edge d’accès ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, access.contoso.com).
    
    > [!NOTE]  
    > Dans Lync Server 2013, cette condition n’est plus obligatoire, mais il est conseillé de la respecter pour assurer la compatibilité avec Office Communications Server.

  - La liste des autres noms de sujet contient les noms de domaines complets des éléments suivants :
    
      - l’interface externe du service Edge d’accès ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, access.contoso.com) ;
        
        > [!NOTE]  
        > Même si le nom de sujet du certificat est le même que le nom de domaine complet du serveur Edge d’accès, l’autre nom du sujet doit également contenir le nom de domaine complet du serveur Edge d’accès, car le protocole TLS (Transport Layer Security) ignore le nom du sujet et utilise les entrées des autres noms de sujet pour la validation.    
      - l’interface externe du serveur Edge de conférence web ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, webcon.contoso.com) ;
    
      - Si vous faites appel à la fédération ou à la configuration automatique des clients, incluez également les noms de domaines complets SIP utilisés dans votre entreprise (par exemple, sip.contoso.com, sip.fabrikam.com).
    
      - Le service Edge A/V n’utilise pas le nom du sujet ou les entrées d’autres noms du sujet.
    
    > [!NOTE]  
    > L’ordre des noms de domaines complets dans la liste des autres noms de sujet n’a pas d’importance.

Si vous déployez plusieurs serveurs Edge à charge équilibrée sur un site, le certificat du service d’authentification A/V installé sur chaque serveur Edge doit provenir de la même autorité de certification et utiliser la même clé privée. Il est à noter que la clé privée du certificat doit pouvoir être exportée, qu’elle soit utilisée sur un ou plusieurs serveurs Edge. Elle doit pouvoir être exportée si vous demandez le certificat à un ordinateur autre que le serveur Edge. Comme le service d’authentification A/V n’utilise pas le nom du sujet ni un autre nom du sujet, vous pouvez réutiliser le certificat Edge d’accès, pourvu que les conditions liées au nom du sujet et aux autres noms du sujet sont remplies pour le serveur Edge d’accès et le serveur Edge de conférence web et que la clé privée du certificat puisse être exportée.

Les conditions requises pour l’utilisation d’un certificat privé (ou public) pour l’interface interne du serveur Edge sont les suivantes :

  - Le certificat peut être émis par une autorité de certification interne ou une autorité de certification publique approuvée.

  - Le nom de sujet du certificat est généralement le nom de domaine complet de l’interface interne du serveur Edge ou l’adresse IP du programme d’équilibrage de la charge matérielle (par exemple, lsedge.contoso.com). Mais vous pouvez utiliser un certificat générique sur l’interface interne du serveur Edge.

  - Aucune liste des autres noms de sujet n’est requise.

Les exigences du proxy inverse de vos services de déploiement sont les suivantes :

  - accès utilisateur externe au contenu de réunion pour les réunions ;

  - accès utilisateur externe au développement et à l’affichage des membres des groupes de distribution ;

  - accès utilisateur externe aux fichiers téléchargeables du service de carnet d’adresses ;

  - accès utilisateur externe au client Lync Web App ;

  - accès utilisateur externe à la page web des paramètres de configuration des conférences rendez-vous ;

  - accès utilisateur externe au service Informations d’emplacement ;

  - accès périphérique externe au service de mise à jour des périphériques et obtention des mises à jour.

Le proxy inverse publie les URL des composants web de serveur interne. Les URL des composants web sont définies sur le directeur, le serveur frontal ou le pool de serveurs frontaux en tant que **Services web externes** dans l’Générateur de topologie.

Les entrées avec caractères génériques sont prises en charge dans le champ d’autre nom de sujet du certificat affecté au proxy inverse. Pour plus d’informations sur la configuration de la demande de certificat pour le proxy inverse, reportez-vous à [Demande et configuration d’un certificat pour votre proxy HTTP inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

## Voir aussi

#### Concepts

[Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

