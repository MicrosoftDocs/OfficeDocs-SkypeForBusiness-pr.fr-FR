---
title: 'Lync Server 2013 : Activation d’Office Web Apps Server et Lync Server 2013'
TOCTitle: Activation d’Office Web Apps Server et Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204792(v=OCS.15)
ms:contentKeyID: 49296816
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’intégration à Office Web Apps Server et Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 utilise Office Web Apps Server pour gérer les présentations PowerPoint. Pour plus d’informations sur les avantages de cette approche, reportez-vous à [Vue d’ensemble des conférences web dans Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Pour pouvoir utiliser ces nouvelles fonctionnalités, les administrateurs doivent installer Office Web Apps Server et configurer Lync Server 2013 pour qu’il communique avec Office Web Apps Server. Cette documentation fournit des informations sur la configuration de Lync Server 2013 pour qu’il fonctionne avec Office Web Apps Server, mais elle ne fournit pas d’informations sur la façon d’installer Office Web Apps Server à proprement parler. Ces informations sont disponibles sur le site web du déploiement Microsoft Office Web Apps à l’adresse [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x40c). Ce guide inclut une description complète des conditions requises nécessaires pour Office Web Apps Server. Notez que Office Web Apps Server doit être installé sur un ordinateur autonome qui n’exécute pas Lync Server, Microsoft SQL Server ou toute autre application serveur. (Aucune version de Microsoft Office ne doit être installée sur cet ordinateur.) Tout ordinateur utilisé pour exécuter Office Web Apps Server doit aussi posséder un ensemble spécifique de logiciels installés (dont .NET Framework 4.5 et Windows PowerShell 3.0). Ces conditions requises, de même que les informations sur la configuration des certificats et des services Internet (IIS), sont détaillées sur le site web du déploiement Microsoft Office Web Apps à l’adresse [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x40c).

Ce document couvre les domaines suivants :

  - [Configuration de Lync Server 2013 pour le fonctionnement avec Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Publication d’Office Web Apps Server dans Lync Server 2013 avec un serveur proxy inverse](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Validation de la configuration d’Office Web Apps Server dans Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configuration des clients dans Lync Server 2013 pour l’utilisation avec Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

