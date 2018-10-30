---
title: 'Lync Server 2013 : intégration à Microsoft Exchange Server 2013'
TOCTitle: Intégration de Lync Server 2013 à Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49891401
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Intégration de Microsoft Lync Server 2013 à Microsoft Exchange Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Exchange et Lync Server ont un long passé d’intégration et de compatibilité. Cette intégration se remarque le plus dans leur application cliente respective. Par exemple, les informations de présence de Lync peuvent être signalées dans Microsoft Outlook ; de même, Lync peut utiliser le calendrier Outlook pour mettre automatiquement à jour ces informations de présence. (Par exemple, Lync peut changer votre statut en Occupé(e) dès que votre calendrier indique que vous avez une réunion planifiée.) Même s’il n’est pas nécessaire d’exécuter Exchange afin d’exécuter Lync Server (ou inversement), il est indéniable que l’utilisation conjointe des deux produits illustre parfaitement l’adage « l’union fait la force ».

Cela se vérifie particulièrement avec le lancement de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013. Outre les fonctionnalités comme la messagerie unifiée, la messagerie instantanée et la présence, disponibles dans Microsoft Exchange Server 2010 et Microsoft Lync Server 2010, les versions 2013 des produits serveur incluent plusieurs nouvelles fonctions. Ces dernières incluent notamment les suivantes :

  - **Intégration de l’archivage Lync**. Dans Lync Server 2013, les administrateurs ont encore la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence web dans SQL Server (de la même manière que ces transcriptions le sont dans Lync Server 2010). En revanche, ils peuvent également choisir d’archiver les transcriptions dans Exchange 2013, en les stockant dans les boîtes aux lettres individuelles des utilisateurs de la même manière qu’Exchange archive les communications. Cela signifie qu’un seul référentiel est nécessaire pour toutes les communications électroniques (d’Exchange et de Lync Server), ce qui facilite grandement la recherche et la récupération des communications archivées en cas de besoin.

  - **Magasin de contacts unifié**. Dans Lync Server 2010, les utilisateurs devaient gérer des listes de contacts distinctes dans Outlook et Lync ; en fait, pour être sûr de disposer des mêmes contacts dans les deux produits, vous deviez gérer des listes de contacts dupliquées, une pour Outlook et une pour Lync. Avec Lync Server 2013, en revanche, il est possible de stocker les contacts des utilisateurs dans Exchange 2013 et dans le magasin de contacts unifié. L’utilisation d’un seul magasin de contacts permet aux utilisateurs de gérer un seul ensemble de contacts, lequel est disponible dans Lync 2013, Outlook 2013 et Outlook Web Access 2013.

  - **Planification de réunions Lync à partir d’OWA** . Avec l’intégration de Lync Server 2013 et de Exchange 2013, les utilisateurs peuvent planifier des réunions Lync à partir d’Outlook Web Access 2013.

  - **Photos haute résolution**. Lync 2010 permettait uniquement d’afficher de petites photos de vos contacts car ces photos étaient stockées dans Active Directory et Active Directory impose une limite de 48 pixels par 48 pixels aux photos stockées. Avec Lync Server 2013, en revanche, il est possible de stocker des photos dans Microsoft Exchange, ce qui permet d’utiliser des photos haute résolution dont la taille peut s’élever jusqu’à 648 pixels par 648 pixels. Comme vous pouvez vous en douter, Lync 2013 a été mis à niveau de sorte à autoriser l’affichage de ces photos haute résolution.

N’oubliez pas que ces nouvelles fonctionnalités requièrent l’utilisation de Lync Server 2013 ET Exchange 2013. En outre, les utilisateurs qui espèrent tirer pleinement parti de ces nouvelles fonctions doivent posséder des comptes sur Lync Server 2013 et Exchange 2013, et ils doivent utiliser les dernières versions des logiciels clients (par ex., Lync 2013). À titre d’exemple, le magasin de contacts unifié n’est pas disponible pour les utilisateurs qui ont été hébergés sur Lync Server 2010 ; de même, il n’est pas possible d’afficher des photos haute résolution dans Lync 2010.

Cette documentation fournit des informations sur l’intégration de Lync Server 2013 et Exchange 2013, notamment des instructions pas à pas sur l’activation des nouvelles fonctionnalités telles que l’intégration de l’archivage et le magasin de contacts unifié. En revanche, cette documentation ne décrit pas l’installation et la configuration initiales de ces deux produits. Pour plus d’informations sur le déploiement de Lync Server 2013, reportez-vous au site TechCenter de Lync Server 2013 à l’adresse [http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0x40c). Pour plus d’informations sur le déploiement de Exchange 2013, reportez-vous au site TechCenter de Exchange 2013 à l’adresse [http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0x40c).

## Dans cette section

[Configuration requise pour l’intégration de Microsoft Lync Server 2013 et Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configuration des applications partenaires dans Microsoft Lync Server 2013 et Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configuration de Microsoft SharePoint Server 2013 pour la recherche des données Microsoft Lync Server 2013 archivées](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configuration de Microsoft Lync Server 2013 pour l’utilisation du magasin de contact unifié](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configuration de la messagerie unifiée Microsoft Exchange Server 2013 pour la messagerie vocale Microsoft Lync Server 2013](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Intégration de Microsoft Lync Server 2013 et Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

