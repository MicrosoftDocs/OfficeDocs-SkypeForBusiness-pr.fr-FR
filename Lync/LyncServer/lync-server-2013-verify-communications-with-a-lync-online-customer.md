---
title: Vérifier les communications avec un client Lync Online
TOCTitle: Vérifier les communications avec un client Lync Online
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202189(v=OCS.15)
ms:contentKeyID: 49298803
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérifier les communications avec un client Lync Online

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour permettre aux utilisateurs Lync de votre organisation de communiquer avec les utilisateurs d’un client Microsoft Lync Online 2010, vous devez avoir exécuté les étapes suivantes :

  - Toutes les conditions préalables sont satisfaites : vous avez déployé vos serveurs internes et Edge, activé la prise en charge de la fédération pour votre organisation et configuré des comptes d’utilisateurs. Pour plus d’informations, voir [Conditions préalable à la fédération avec un client Lync Online](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).

  - Vous avez configuré la prise en charge de l’accès au domaine dans votre déploiement interne. Cela consiste notamment à créer une entrée de fournisseur hôte et à configurer votre déploiement afin d’autoriser l’accès à partir du domaine du client Lync Online. Pour plus d’informations, voir [Configurer la prise en charge de la fédération pour un domaine Lync Online](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).

  - Vous avez configuré les comptes de vos utilisateurs de sorte qu’ils prennent en charge la fédération. Pour plus d’informations, voir [Configurer l’accès utilisateur pour la fédération avec un client Lync Online](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).

Après avoir accompli toutes ces étapes et vous être assuré que l’administrateur du client Lync Online 2010 a entièrement configuré ses services en ligne en vue d’une prise en charge de la fédération avec votre organisation, procédez à des essais en testant la communication entre un utilisateur interne de votre organisation et un utilisateur du client Lync Online. Si vous ne parvenez pas à établir de communication, utilisez l’outil de journalisation de votre serveur Edge pour résoudre le problème à l’aide des fichiers journaux et de suivi. Pour plus d’informations sur l’utilisation de l’outil de journalisation, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations. Pour plus d’informations sur l’outil de journalisation, voir la documentation Outil de journalisation Lync Server 2010 dans la bibliothèque TechNet à l’adresse [http://go.microsoft.com/fwlink/?linkid=199265\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=199265%26clcid=0x40c).

