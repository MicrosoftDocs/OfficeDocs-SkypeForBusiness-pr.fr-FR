---
title: 'Lync Server 2013 : fonctionnalités et fonctionnalités de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a001a6fb76a0612f7f650a31de5cf788a7f69327
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Fonctionnalités et fonctionnalités de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 prend en charge les fonctionnalités des clients mobiles Lync 2010 mobile et Lync 2013. Lorsque vous déployez le service de mobilité Lync Server 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone, ou Nokia Symbian, pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. Les nouvelles fonctionnalités introduites dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 incluent la fonctionnalité voix sur IP (VoIP) et la vidéo (H. 264) pour le participant à la réunion.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 : février 2013 prend en charge la fonctionnalité de client mobile Lync 2013. Les mises à jour cumulatives pour Lync Server 2013 : février 2013 installer l’API Web de communications unifiées ou UCWA. UCWA est le composant utilisé pour les clients mobiles Lync 2013. Dans Lync Server 2013, MCX est utilisé pour les clients mobiles Lync 2010. Mises à jour cumulatives pour Lync Server 2013 : février 2013 introduire UCWA comme nouveau point d’entrée pour les services de mobilité. Lync Server 2013 implémente simultanément le service de mobilité (MCX), introduit dans les mises à jour cumulatives pour Lync Server 2010 : novembre 2011, et prend en charge Lync 2010 mobile. Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013 : février 2013, les utilisateurs peuvent utiliser des périphériques mobiles Apple iOS, Android et Windows Phone pris en charge pour effectuer les opérations suivantes :

<div>


> [!IMPORTANT]  
> Les fonctionnalités prises en charge par le service de mobilité à partir des mises à jour cumulatives pour Lync Server 2010 : novembre 2011 sont indiquées par (MCX). Toutes les fonctionnalités répertoriées sont prises en charge par le UCWA, introduites dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

  - Envoyer et recevoir des messages instantanés (MCX)

  - Afficher la présence (MCX)

  - Afficher les contacts (MCX)

  - Cliquez pour participer à une conférence (MCX)

  - Appel via le bureau (MCX)

  - Un seul numéro atteint (MCX)

  - Messagerie vocale (MCX)

  - Notification d’appel manqué (MCX)

  - Voix sur IP (VoIP)

  - Vidéo des participants (H. 264)

<div>


> [!NOTE]  
> Lync 2010 mobile a fourni un client pour les appareils Nokia Symbian. Lync 2013 mobile ne disposera pas d’un client pour les appareils basés sur Nokia Symbian.



</div>

Les utilisateurs d’appareils Apple iPad auront accès aux fonctionnalités améliorées. Après avoir rejoint une réunion à l’aide de l’audio de rappel, un utilisateur de iPad pourra visualiser les présentations Microsoft PowerPoint téléchargées au sein d’une réunion, partager des applications et des bureaux, afficher la liste des participants à la réunion et recevoir des notifications d’autres types de contenu. qui sont partagés au sein de la réunion.

<div>


> [!TIP]  
> Grâce au numéro unique, un utilisateur reçoit les appels qui ont été passés en composant son numéro professionnel sur son téléphone portable. Avec l’appel via le bureau, l’utilisateur passe un appel sortant depuis le client Lync mobile en utilisant un numéro de téléphone professionnel au lieu du numéro de téléphone mobile. Avec les appels sortants, le client envoie une demande à MCX ou UCWA (en fonction de la version de Lync mobile) pour effectuer les appels. Le serveur lance l’appel, puis rappelle l’utilisateur sur son téléphone mobile. Lorsque ce dernier répond, le serveur termine l’appel en composant le numéro de l’interlocuteur. L’utilisation de l’appel via le bureau permet aux utilisateurs de conserver leur identité professionnelle pendant un appel, ce qui signifie que le destinataire de l’appel ne voit pas le numéro de portable de l’appelant, et ce dernier évite ainsi les frais d’appel sortant encourus.



</div>

<div>


> [!NOTE]  
> Les fonctionnalités ne fonctionnent pas toutes de la même manière sur tous les appareils mobiles. Pour plus d’informations sur les fonctionnalités prises en charge sur les appareils mobiles, consultez <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>les tableaux de comparaison des clients mobiles à l’adresse. Pour plus d’informations sur les appareils pris en charge et les systèmes d’exploitation, voir les rubriques relatives aux conditions requises sous <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.



</div>

Lorsque vous utilisez la fonctionnalité de découverte automatique Lync Server 2013, les applications mobiles peuvent localiser automatiquement les services Web Lync Server 2013 sans que les utilisateurs aient besoin d’entrer manuellement les URL dans les paramètres de leurs appareils. La saisie manuelle des URL dans les paramètres d’un appareil mobile est également prise en charge, principalement à des fins de résolution des problèmes.

<div>


> [!IMPORTANT]  
> MCX et UCWA sont des services gratuits et sont déployés pour prendre en charge les clients mobiles Lync 2010 mobile et Lync 2013. Lync 2013 mobile ne pourra pas se connecter aux déploiements Lync Server 2010. Lync 2010 mobile et Lync 2013 mobile seront en mesure d’utiliser un déploiement Lync Server 2013 avec les mises à jour cumulatives pour Lync Server 2013 : février 2013 appliquée.



</div>

La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification qui est envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active. Par exemple, une invitation de messagerie instantanée manquée peut entraîner une notification de transmission.

MCX, UCWA, le service de découverte automatique et la prise en charge des notifications de type transmission sont fournis dans Lync Server 2013. Les fonctionnalités client mises à jour, les fonctionnalités et l’utilisation de UCWA comme point d’entrée de mobilité sont présentées dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.

</div>

<span> </span>

</div>

</div>

</div>

