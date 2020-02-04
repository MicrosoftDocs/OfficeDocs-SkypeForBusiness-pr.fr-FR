---
title: 'Lync Server 2013 : vérification des journaux des événements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Vérification des journaux des événements dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-06_

Vous pouvez utiliser l' [Observateur d’événements Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) pour afficher les journaux d’événements et obtenir des informations sur les échecs de service, les erreurs de réplication dans les services de domaine Active Directory et les avertissements relatifs aux ressources système, tels que la mémoire virtuelle et l’espace disque. Le visionneuse d’événements est incluse dans Windows Server 2008 et 2012.

Dans l’outil de journalisation de Lync Server 2013, lorsque vous mettez fin à la session de débogage, cliquez sur **analyser les fichiers journaux** pour afficher les fichiers journaux à l’aide de l’outil Snoop.

L’observateur d’événements gère les journaux des événements d’application, de sécurité et de système sur l’ordinateur. Il s’agit de Lync Server 2013 et de Windows, et de signaler des erreurs aux journaux des événements. Par conséquent, révisez les journaux d’événements quotidiennement.

Utilisez l’observateur d’événements pour :

  - Afficher et gérer les journaux d’événements.

  - Obtenez des informations sur les problèmes liés au matériel, au logiciel et au système qui doivent être résolus.

  - Identifiez les tendances qui nécessitent une action ultérieure.

Un serveur exécutant Lync Server sur un système d’exploitation Windows Server enregistre les événements dans quatre types de journaux :

  - **Journaux d’application**   le journal de l’application contient les événements enregistrés par des applications ou des programmes. Les développeurs déterminent les événements à consigner. Par exemple, un programme de base de données peut enregistrer une erreur de fichier dans le journal de l’application. La plupart des événements associés à Lync Server 2013 apparaissent dans le journal des applications.

  - **Journaux**   de sécurité le journal de sécurité enregistre les événements tels que valides et non valides pour les tentatives en plus d’événements liés à l’utilisation des ressources, comme la création, l’ouverture ou la suppression de fichiers ou d’autres objets. Par exemple, si l’audit d’ouverture de session est activé, les tentatives de connexion au système sont enregistrées dans le journal de sécurité.

  - **Journal système enregistre**   le journal système contient des événements enregistrés par les composants du système Windows. Par exemple, l’échec du chargement d’un pilote ou d’un autre composant système lors du démarrage est enregistré dans le journal système. Les types d’événements enregistrés par les composants système sont prédéterminés par le serveur.

  - **Lync Server 2013**   l’outil d’enregistrement enregistre des événements importants liés à l’authentification, aux connexions et aux actions de l’utilisateur. Après l’activation de la journalisation des diagnostics, vous pouvez afficher les entrées du journal dans l’observateur d’événements.

<div>


> [!NOTE]  
> Nous vous déconseillons d’utiliser les paramètres d’enregistrement maximum sauf si vous y êtes invité par les services d’assistance technique Microsoft. La journalisation maximale draine les ressources importantes et peut proposer de nombreux « faux positifs », c’est-à-dire des erreurs qui ne sont pas enregistrées uniquement dans le journal maximal, mais qui ne sont pas à l’origine du problème. Nous vous recommandons également de ne pas activer la journalisation des diagnostics de manière définitive. Utilisez-le uniquement lors de la résolution des problèmes.



</div>

Dans chaque journal de l’observateur d’événements, Lync Server 2013 enregistre les événements d’information, d’avertissement et d’erreur. Contrôlez soigneusement ces journaux pour suivre les types de transactions effectuées sur les serveurs Lync Server 2013. Vous devez archiver périodiquement les journaux ou utiliser la fonctionnalité de substitution automatique pour éviter de manquer d’espace. Étant donné que les fichiers journaux peuvent occuper une quantité limitée d’espace, augmentez la taille du journal (par exemple, à 50 Mo) et configurez-le pour que le serveur Lync Server 2013 puisse continuer à rédiger de nouveaux événements.

Vous pouvez également automatiser l’administration du journal des événements en utilisant les outils et technologies suivants :

  - System Center Operations Manager surveille l’intégrité et l’utilisation des serveurs Lync Server 2013. Lync Server 2013 Management Pack pour Operations Manager étend Operations Manager en fournissant un contrôle spécialisé pour les serveurs exécutant Lync Server 2013.

  - Le pack d’administration de Lync Server 2013 pour Operations Manager surveille les éditions standard et entreprise de Lync Server 2013. Cette version inclut également le pack d’administration de qualité de l’interface (QoE) qui était auparavant un module d’administration distinct.

Les types surveillés sont les entrées du journal des événements, les compteurs de performance et la surveillance dynamique de QoE. Cette version du pack d’administration analyse uniquement Lync Server 2013 et 2010 et ne peut pas être utilisée pour surveiller Office Communications Server 2007.

Le pack d’administration offre les fonctionnalités suivantes :

  - Alertes indiquant un service affectant des événements

  - Alertes indiquant la configuration et autres problèmes d’impact sur les autres services

  - Surveiller l’état des services Lync Server

  - Connaissances du produit : cause et résolution des problèmes identifiés

Pour plus d’informations sur le pack d’administration 2013 de Lync Server, voir [analyse de Lync server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Peigne**   d’événement l’outil peignement d’événement collecte des événements spécifiques provenant des journaux d’événements de plusieurs ordinateurs à un emplacement central. Elle vous permet de signaler uniquement les ID d’événement ou les sources d’événements qu’elle spécifie. Pour plus d’informations sur le peigne d’événement, voir le site Web des [outils de verrouillage et de gestion des comptes](http://go.microsoft.com/fwlink/?linkid=35607) .

**Déclencheurs d’événements**   dans Windows Server 2012 vous pouvez « joindre une tâche à cet événement » dans l’observateur d’événements Windows, où un administrateur peut exécuter un programme, envoyer un message électronique ou afficher un message visuel. Pour plus d’informations sur cette fonctionnalité, voir la rubrique Windows Server 2008 R2 [exécuter une tâche en réponse à un événement donné](http://technet.microsoft.com/en-us/library/cc748900.aspx). Vous pouvez également utiliser des outils de ligne de commande tels que’EventTrigger. exe’pour créer et interroger des journaux d’événements, et associer des programmes à des événements enregistrés spécifiques. À l’aide de Eventtriggers. exe, vous pouvez créer des déclencheurs d’événements qui exécutent des programmes lorsque des événements spécifiques se produisent.

<div>

## <a name="see-also"></a>Voir aussi


[Observateur d’événements Windows](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

