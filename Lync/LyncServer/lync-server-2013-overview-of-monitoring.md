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
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Vue d’ensemble de l’analyse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-05_

Dans Microsoft Lync Server 2013, le contrôle permet de collecter les informations d’utilisation et les données de qualité d’utilisation (QoE) sur les sessions de communication auxquelles les utilisateurs participent. Une session est un terme générique qui couvre la connexion d’un utilisateur à :

  - Conférence

  - Modalité de conférences (par exemple, audio/vidéo ou partage d’applications)

  - un autre utilisateur via une conversation P2P (comme la messagerie instantanée ou un appel audio).

<div>


> [!NOTE]  
> Lync Server 2013 effectue le suivi des informations relatives à chaque session : qui a appelé qui ; Quels points de terminaison utilisés dans la session ; durée de la session, Quelle a été la qualité perçue de la session ; et ainsi de suite. Toutefois, Lync Server n’enregistre et ne stocke pas l’appel réel. Qui inclut également des sessions de messagerie instantanée : bien que Lync Server enregistre des informations sur les sessions de messagerie instantanée, il ne conserve aucun enregistrement de chaque message instantané envoyé lors de la session.



</div>

Les informations détaillées des appels collectées par Lync Server peuvent être utilisées pour n’importe quel nombre d’usages, y compris :

  - **Retour sur investissement**. Les administrateurs peuvent comparer les données d’utilisation collectées par Monitoring Server à des données similaires collectées pour leur précédent système de téléphonie afin d’afficher des économies de coûts et de justifier le déploiement de Lync Server.

  - La **Gestion des stocks de périphériques**. Les informations sur la gestion des ressources permettent aux administrateurs d’identifier les anciens appareils toujours en cours d’utilisation qui doivent être remplacés, ainsi que d’identifier les appareils coûteux qui ne semblent pas être utilisés du tout.

  - Support technique. Les données de dépannage permettent aux ingénieurs de la prise en charge de déterminer la raison pour laquelle l’appel d’un utilisateur a échoué et de ne pas avoir à collecter les journaux côté serveur ou client. Il est possible d’accéder à ces informations et de les comprendre par le personnel du support technique disposant d’une connaissance technique approfondie de Microsoft Lync 2013 et de Lync Server 2013.

  - **Identification et résolution des problèmes du système**. Permet aux administrateurs de détecter les problèmes majeurs qui peuvent empêcher les utilisateurs finaux d’effectuer des tâches de base comme la participation à une conférence, l’émission d’un appel ou l’envoi d’un message instantané.

En plus de ces informations de base, le serveur de surveillance fournit également un mécanisme qui permet aux points de terminaison SIP (par exemple, Lync 2013) de fournir des informations de dépannage auxquelles le serveur n’aura pas accès.

  - **Mesures qui affectent la qualité**. Ces mesures traitent la transmission effective de l’appel. ils fournissent ainsi une sorte de journaux de voyages lors du déplacement de l’appel sur le réseau. Ces mesures (qui incluent des éléments tels que la perte de paquets, la gigue et les temps d’aller-retour) fournissent des informations sur ce qui est arrivé à l’appel à partir du moment où il est parvenu au point de terminaison de l’autre personne.

  - **Problèmes signalés à l’utilisateur final**. Ces mesures incluent des notifications de bonne qualité que Lync 2013 présenter aux utilisateurs finaux dans les cas où ceux-ci sont trop éloignés d’un micro, parlant trop de manière modérée, disposant d’une connexion réseau médiocre ou dont la qualité est médiocre, car un autre programme de l’ordinateur est utilisation des ressources disponibles.

  - **Informations sur l’environnement**. Ces mesures détaillent des facteurs de qualité d’appel, notamment le type de micro et les haut-parleurs utilisés, si l’utilisateur est connecté via une connexion VPN et si l’utilisateur utilise une connexion sans fil.

À la fin de chaque appel, des points de terminaison compatibles SIP transmettent automatiquement ces informations au serveur frontal qui facilite l’appel. Aucune opération n’est nécessaire pour que les points de terminaison transmettent ces informations ; ce comportement est intégré au protocole SIP. Cependant, si vous souhaitez collecter et stocker ces informations, vous devez installer et activer la surveillance. Si vous installez et activez la surveillance, les informations relatives aux appels sont collectées par des agents exécutés sur le serveur frontal et relayées à une paire de bases de données SQL Server.

Notez que le processus d’installation et de configuration de la surveillance a été simplifié dans Lync Server 2013. Dans les versions antérieures du logiciel, la surveillance nécessitait un rôle serveur de surveillance distinct, qui signifiait en général un autre ordinateur mis en réserve pour une utilisation comme serveur de surveillance. Par le biais de Lync Server 2013, le rôle serveur de surveillance a été supprimé. Au lieu de cela, le service de surveillance (qui se présente sous la forme d’agents de collection de données unifiées) a été colocalisé sur tous les serveurs frontaux. Vous avez au moins deux avantages principaux. Colocalisation du service de surveillance :

  - Réduit le nombre de rôles de serveur requis lors de l’implémentation de Lync Server 2013. Le fait de décrémenter le rôle du serveur de surveillance permet également de réduire les coûts en éliminant le besoin de mettre à jour les serveurs dédiés pour la surveillance.

  - Simplifie la configuration et l’administration de Lync Server 2013. En collocatingant les services de surveillance sur chaque serveur frontal, vous n’avez plus besoin d’installer, de configurer et de gérer le rôle du serveur de surveillance.

Pour plus d’informations, reportez-vous à la rubrique [déploiement de la surveillance dans Lync server 2013](lync-server-2013-deploying-monitoring.md) dans le Guide de déploiement de lync Server 2013 2013.

</div>

<span> </span>

</div>

</div>

</div>

