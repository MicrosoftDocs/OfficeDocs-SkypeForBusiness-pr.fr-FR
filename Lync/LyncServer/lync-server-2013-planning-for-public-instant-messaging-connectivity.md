---
title: Planification de la connectivité PIC (Public Instant Messaging Connectivity)
TOCTitle: Planification de la connectivité PIC (Public Instant Messaging Connectivity)
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205349(v=OCS.15)
ms:contentKeyID: 49299206
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la connectivité PIC (Public Instant Messaging Connectivity)

 

_**Dernière rubrique modifiée :** 2017-03-09_

La Connectivité PIC (Public IM Connectivity) est une classe de fédération configurée pour permettre à vos utilisateurs internes et externes de Lync Server 2013 d’ajouter des contacts à partir des applications suivantes :

  - Contacts Messenger

  - Contacts Yahoo\!

  - Contacts AOL (America Online)

> [!IMPORTANT]  
> <ul>
> <li><p>Depuis le 1er septembre 2012, la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service. Une date de fin de vie de juin 2014 a été annoncée pour AOL et Yahoo! Pour plus d’informations, voir <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013</a>.</p></li>
> <li><p>La licence PIC USL est une licence d’abonnement mensuel par utilisateur requise pour la fédération de Lync Server ou Office Communications Server avec Yahoo! Messenger. La capacité de Microsoft à fournir ce service est liée au soutien de Yahoo!, dont le contrat sous-jacent ne sera pas renouvelé.</p></li>
> <li><p>Lync est un outil puissant permettant aux organisations et aux individus du monde entier de rester connectés. La fédération avec Windows Live Messenger ne nécessite aucune licence utilisateur/appareil supplémentaire en plus de la licence d’accès client (CAL) standard Lync. La fédération avec Skype sera prochainement ajoutée à cette liste, ce qui permettra aux utilisateurs Lync d’entrer en contact avec des centaines de millions de personnes à l’aide des fonctionnalités vocales et de messagerie instantanée.</p></li></ul>


Cette classe de fédération nécessite les considérations de planification suivantes :

  - Les utilisateurs de Windows Live Messenger peuvent communiquer avec l’audio/la vidéo d’égal-à-égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée. Vos serveurs Edge doivent respecter des exigences de port et de protocole spécifiques. Pour plus d’informations, voir [Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messagerie instantanée Yahoo n’a aucune exigence spécifique autre que celles typiquement utilisées dans la planification et le déploiement d’un serveur Edge classique qui fournit la fédération.

  - America Online demande à ce que votre certificat serveur Edge attribué au service Edge d’accès ait une utilisation améliorée de la clé (EKU).

## Dans cette section

  - [Résumé des certificats - Connectivité PIC (Public IM Connectivity)](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Résumé des ports - Connectivité PIC (Public IM Connectivity)](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [Résumé des enregistrements DNS - Connectivité PIC (Public IM Connectivity)](https://technet.microsoft.com/fr-fr/library/jj618375\(v=ocs.15\))

