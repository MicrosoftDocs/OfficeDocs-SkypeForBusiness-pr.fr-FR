---
title: 'Lync Server 2013 : Prise en charge de la messagerie instantanée publique'
TOCTitle: Prise en charge de la messagerie instantanée publique
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204732(v=OCS.15)
ms:contentKeyID: 49296457
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de la messagerie instantanée publique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-10-07_

Lync Server 2013 prend en charge l’utilisation de fournisseurs de services de messagerie instantanée publics sous licence, ainsi que l’utilisation du protocole XMPP (Extensible Messaging and Presence Protocol) pour mettre en œuvre un type particulier de fédération permettant à Lync Server d’accéder à des partenaires du domaine XMPP configuré à l’aide du client Lync 2013.

## Prise en charge des fournisseurs de services de messagerie instantanée publics

Les partenaires de connectivité PIC (Public Instant Messaging) actuellement pris en charge sont les suivants :

  - America Online

  - Windows Live

  - Yahoo\!

Concernant les communications avec les utilisateurs Windows Live, Lync Server 2013 prend en charge la messagerie instantanée P2P, ainsi que les appels audio et vidéo. Concernant les communications avec AOL et Yahoo\!, Lync Server 2013 prend en charge la messagerie instantanée P2P. Une licence distincte peut être nécessaire.

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, reportez-vous à <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent arrive à expiration.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


## Prise en charge de la fédération XMPP

La fédération XMPP prend en charge la communication des utilisateurs Lync avec les utilisateurs du domaine XMPP configuré qui utilisent un fournisseur public, tel que GTalk. Les communications avec ces utilisateurs peuvent inclure :

  - la messagerie instantanée P2P et la présence ;

  - Création de contacts fédérés XMPP dans le client Lync

