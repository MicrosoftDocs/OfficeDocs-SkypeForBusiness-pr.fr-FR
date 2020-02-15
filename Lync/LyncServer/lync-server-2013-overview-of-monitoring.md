---
title: 'Lync Server 2013 : vue d’ensemble de la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa0d3ed6b83d610ee4d92c76487f2dbfb50f89e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Vue d’ensemble de la surveillance dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Dans Microsoft Lync Server 2013, la surveillance est utilisée pour collecter des informations sur l’utilisation et des données de qualité de l’expérience (QoE) sur les sessions de communication auxquelles vos utilisateurs sont impliqués. Une session est un terme générique qui couvre la connexion d’un utilisateur à un :

  - Salle

  - Modalité de conférence (comme l’audio/vidéo ou le partage d’application)

  - Un autre utilisateur via une conversation d’égal à égal telle qu’une messagerie instantanée ou un appel audio

<div>


> [!NOTE]  
> Lync Server 2013 effectue le suivi des informations relatives à chaque session : qui a appelé personne ; Quels points de terminaison ont été utilisés dans la session ; la durée de la dernière session ; quelle était la qualité perçue de la session ; et ainsi de suite. Toutefois, Lync Server n’enregistre pas et ne stocke pas l’appel réel lui-même. Cela inclut également les sessions de messagerie instantanée : même si Lync Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve pas d’enregistrement de chaque message instantané envoyé pendant la session.



</div>

Les informations détaillées sur l’appel collectées par Lync Server peuvent être utilisées pour n’importe quel nombre d’utilisations, notamment :

  - **Retour sur investissement (roi)**. Les administrateurs peuvent comparer les données d’utilisation collectées par le serveur de surveillance aux données similaires collectées pour leur système de téléphonie précédent afin d’afficher des économies de coûts et de justifier le déploiement de Lync Server.

  - **Gestion**de l’inventaire des appareils. Les informations de gestion des biens aident les administrateurs à identifier les anciens appareils encore en cours d’utilisation qui doivent être remplacés, ainsi qu’à identifier les appareils onéreux qui ne semblent pas être utilisés du tout.

  - Support technique. Les données de dépannage permettent aux ingénieurs de la prise en charge de déterminer pourquoi l’appel d’un utilisateur a échoué, et de le faire sans avoir à collecter les journaux côté serveur ou côté client. Ces informations sont facilement accessibles et compréhensibles par le personnel du support technique qui ne possède pas de connaissances techniques approfondies de Microsoft Lync 2013 et Lync Server 2013.

  - **Dépannage du système**. Permet aux administrateurs de détecter les problèmes majeurs susceptibles d’empêcher les utilisateurs finaux d’effectuer des tâches de base comme rejoindre une conférence, établir un appel ou envoyer un message instantané.

Outre ces informations d’appel de base, le serveur de surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (par exemple, Lync 2013) de fournir des informations de résolution des problèmes auxquelles le serveur n’a pas accès autrement :

  - **Métriques multimédias ayant un impact sur la qualité**. Ces mesures traitent de la transmission effective de l’appel lui-même ; autrement dit, ils fournissent une sorte de journal de voyage lorsque l’appel passe sur le réseau. Ces mesures (qui incluent notamment des pertes de paquets, des instabilités et des durées d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel entre le moment où il a quitté votre point de terminaison et le moment où il est arrivé au point de terminaison de l’autre personne.

  - **Problèmes signalés à l’utilisateur final**. Ces métriques incluent des notifications de qualité médiocre que Lync 2013 présente aux utilisateurs finaux lorsqu’ils sont trop éloignés d’un microphone, parlant trop peu, ont une mauvaise connexion réseau ou présentent une qualité médiocre, car un autre programme sur l’ordinateur est consommation des ressources disponibles.

  - **Informations sur l’environnement**. Ces critères de qualité des appels de mesure, tels que le type de microphone et les haut-parleurs utilisés, le fait que l’utilisateur est connecté via une connexion VPN et que l’utilisateur se trouve sur une connexion sans fil.

À la fin de chaque appel, les points de terminaison compatibles avec SIP transmettent automatiquement ces informations au serveur frontal qui a facilité l’appel. Vous n’avez rien à faire pour obtenir des points de terminaison afin de transmettre ces informations ; ce comportement est intégré au protocole SIP. Toutefois, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations d’appel sont rassemblées par des agents s’exécutant sur le serveur frontal et relayées vers une paire de bases de données SQL Server.

Notez que le processus d’installation et de configuration de la surveillance a été simplifié dans Lync Server 2013. Dans les versions précédentes du logiciel, la surveillance impliquait un rôle serveur de surveillance distinct, qui signifiait généralement un ordinateur distinct mis de côté pour être utilisé en tant que serveur de surveillance. Dans Lync Server 2013, toutefois, le rôle serveur de surveillance a été éliminé. Au lieu de cela, le service de surveillance (sous la forme d' « agents de collecte de données unifiées ») est colocalisé sur tous les serveurs frontaux. Cela comporte au moins deux avantages majeurs. Colocalisation du service de surveillance :

  - Réduit le nombre de rôles serveur requis lors de l’implémentation de Lync Server 2013. La décrémentation du rôle de serveur de surveillance contribue également à réduire les coûts en supprimant le besoin de maintenir des serveurs dédiés à la surveillance.

  - Réduit la complexité de l’installation et de l’administration de Lync Server 2013. En colocaliser les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle de serveur de surveillance.

Pour plus d’informations, reportez-vous à la rubrique [Deploying Monitoring in Lync server 2013](lync-server-2013-deploying-monitoring.md) dans le Guide de déploiement de lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

