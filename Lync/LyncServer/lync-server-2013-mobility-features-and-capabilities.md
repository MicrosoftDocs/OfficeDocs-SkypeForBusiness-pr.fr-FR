---
title: 'Lync Server 2013 : Fonctionnalités de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Fonctionnalités de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives de Lync Server 2013: février 2013 prend en charge les fonctionnalités des clients mobiles Lync 2010 et Lync 2013. Lorsque vous déployez le service de mobilité Lync Server 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone ou Nokia Symbian pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler par le biais d’un numéro de téléphone, de la messagerie vocale et d’appels manqués. Les nouvelles fonctionnalités intégrées aux mises à jour cumulatives de Lync Server 2013: février 2013 incluent la fonctionnalité de voix sur IP (VoIP) et la vidéo (H. 264) pour les participants à la réunion.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives de Lync Server 2013: février 2013 prend en charge les fonctionnalités de client mobile de Lync 2013. Les mises à jour cumulatives pour Lync Server 2013:2013 février installer l’API Web de communications unifiées ou UCWA. UCWA est le composant utilisé pour les clients mobiles Lync 2013. Dans Lync Server 2013, MCX est utilisé pour les clients mobiles Lync 2010. Mises à jour cumulatives pour Lync Server 2013: février 2013 Introduisez UCWA comme nouveau point d’entrée pour les services de mobilité. Lync Server 2013 implémente simultanément le service de mobilité (MCX), introduit dans les mises à jour cumulatives de Lync Server 2010:2011 novembre, et prend en charge Lync 2010 mobile. Lorsque vous déployez les mises à jour cumulatives pour Lync Server 2013: février 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone pris en charge pour effectuer des activités suivantes:

<div>


> [!IMPORTANT]  
> Les fonctionnalités prises en charge par le service de mobilité par le biais des mises à jour cumulatives pour Lync Server 2010:2011 novembre sont indiquées (MCX). Toutes les fonctionnalités répertoriées sont prises en charge par UCWA, introduites dans les mises à jour cumulatives de Lync Server 2013: février 2013.



</div>

  - Envoyer et recevoir des messages instantanés (MCX)

  - Afficher la présence (MCX)

  - Afficher les contacts (MCX)

  - Cliquez pour participer à une conférence (MCX)

  - Appel via le bureau (MCX)

  - Une seule valeur (MCX)

  - Messagerie vocale (MCX)

  - Notification d’appel manqué (MCX)

  - VoIP

  - Vidéo des participants (H.264)

<div>


> [!NOTE]  
> Lync 2010 mobile proposait un client pour les appareils Nokia Symbian. Lync 2013 mobile n’aura pas de client pour les appareils Nokia Symbian.



</div>

Les utilisateurs d’Apple iPad pourront accéder aux fonctionnalités améliorées. Lorsque vous participez à une réunion à l’aide de la fonction d’appel audio, un utilisateur d’iPad peut afficher les présentations Microsoft PowerPoint téléchargées au sein d’une réunion, partager des applications et des bureaux, afficher la liste des participants à la réunion et recevoir des notifications d’autres types de contenu qui sont partagés au sein de la réunion.

<div>


> [!TIP]  
> Lorsque vous avez atteint le numéro unique, un utilisateur reçoit les appels sur un numéro de téléphone mobile composé du numéro professionnel. Avec la fonction d’appel via le bureau, l’utilisateur passe un appel sortant du client mobile Lync en utilisant un numéro de téléphone professionnel plutôt que le numéro de téléphone mobile. Pour les appels sortants, le client envoie une demande à MCX ou UCWA (en fonction de la version mobile de Lync) pour l’appeler. Le serveur Initialise l’appel, puis le rappelle sur le téléphone mobile. Lorsque l’utilisateur répond, le serveur effectue l’appel en composant un numéro de téléphone. En utilisant les appels via le bureau, les utilisateurs peuvent conserver leur identité professionnelle pendant un appel, ce qui signifie que le destinataire de l’appel n’a pas pu voir le numéro de téléphone mobile de l’appelant et l’appelant évite les frais d’appel sortants.



</div>

<div>


> [!NOTE]  
> Toutes les fonctionnalités ne fonctionnent pas exactement de la même manière sur tous les appareils mobiles. Pour plus d’informations sur les fonctionnalités prises en charge sur les appareils mobiles, voir <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>tableaux de comparaison des clients mobiles à l’adresse. Pour plus d’informations sur les appareils et systèmes d’exploitation pris en charge, voir les rubriques relatives à la configuration <A href="lync-server-2013-planning-for-mobile-clients.md">des clients mobiles dans Lync Server 2013</A>.



</div>

Lorsque vous utilisez la fonctionnalité de découverte automatique de Lync Server 2013, les applications mobiles peuvent automatiquement Rechercher les services Web de Lync Server 2013 sans nécessiter l’entrée manuelle des URL dans les paramètres de l’appareil. La saisie manuelle d’URL dans les paramètres de l’appareil mobile est également prise en charge, principalement à des fins de dépannage.

<div>


> [!IMPORTANT]  
> MCX et UCWA sont des services gratuits qui sont déployés pour prendre en charge les clients mobiles Lync 2010 et Lync 2013. Lync 2013 mobile ne sera pas en mesure de se connecter aux déploiements de Lync Server 2010. Lync 2010 mobile et Lync 2013 mobile pourront utiliser un déploiement Lync Server 2013 avec les mises à jour cumulatives de Lync Server 2013: le 2013 février est appliqué.



</div>

La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active. Par exemple, une invitation à un message instantané manqué peut générer une notification de transmission.

MCX, UCWA, Autodiscover Service et la prise en charge des notifications de transmission sont fournies dans Lync Server 2013. Les fonctionnalités de client mises à jour, les fonctionnalités et l’utilisation de UCWA comme point d’entrée de mobilité sont introduites dans les mises à jour cumulatives de Lync Server 2013: février 2013.

</div>

<span> </span>

</div>

</div>

</div>

