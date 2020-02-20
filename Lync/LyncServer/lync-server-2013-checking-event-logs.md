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
ms.openlocfilehash: 41c49839b01b531c1cd4c9a5eb4cff5fb6a155f4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a>Vérification des journaux des événements dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-06_

Vous pouvez utiliser l' [Observateur d’événements Windows](https://go.microsoft.com/fwlink/p/?linkid=314067) pour afficher les journaux des événements et obtenir des informations sur les défaillances des services, les erreurs de réplication dans les services de domaine Active Directory et les avertissements concernant les ressources système, telles que la mémoire virtuelle et l’espace disque. L’observateur d’événements est inclus dans Windows Server 2008 et 2012.

Dans l’outil de journalisation Lync Server 2013, lorsque vous mettez fin à la session de débogage, cliquez sur **analyser les fichiers journaux** pour afficher les fichiers journaux à l’aide de l’outil Snooper.

L’observateur d’événements gère les journaux relatifs aux événements d’application, de sécurité et système sur l’ordinateur. Lync Server 2013 et Windows signalent les avertissements et les conditions d’erreur dans les journaux des événements. Par conséquent, examinez quotidiennement les journaux des événements.

Utilisez l’observateur d’événements pour :

  - Afficher et gérer les journaux des événements.

  - Obtenir des informations sur les problèmes liés au matériel, aux logiciels et au système qui doivent être résolus.

  - Identifiez les tendances qui nécessitent une action ultérieure.

Un serveur qui exécute Lync Server sur un système d’exploitation Windows Server enregistre les événements dans quatre types de journaux :

  - **Journaux**   des applications le journal des applications contient des événements enregistrés par des applications ou des programmes. Les développeurs déterminent les événements à enregistrer. Par exemple, un programme de base de données peut enregistrer une erreur de fichier dans le journal des applications. La plupart des événements relatifs à Lync Server 2013 apparaissent dans le journal des applications.

  - **Journaux de sécurité**   : le journal de sécurité enregistre des événements tels que les tentatives de connexion valides et non valides en plus des événements liés à l’utilisation des ressources, tels que la création, l’ouverture ou la suppression de fichiers ou d’autres objets. Par exemple, si l'audit d'ouverture de session est activé, les tentatives d'ouverture de session sur le système sont enregistrées dans le journal de sécurité.

  - **Journaux système le**   journal système contient des événements enregistrés par les composants système de Windows. Par exemple, l'échec du chargement d'un pilote ou d'un autre composant système lors du démarrage est enregistré dans le journal système. Les types d'événements consignés par les composant système sont prédéterminés par le serveur.

  - **Lync Server 2013**   l’outil de journalisation enregistre des événements significatifs liés à l’authentification, aux connexions et aux actions de l’utilisateur. Après l’activation de la journalisation des diagnostics, vous pouvez afficher les entrées du journal dans l’observateur d’événements.

<div>


> [!NOTE]  
> Nous vous déconseillons d’utiliser les paramètres de journalisation maximale, sauf si vous y êtes invité par les services de support technique Microsoft. La journalisation maximale épuise les ressources importantes et peut donner de nombreux « faux positifs », c’est-à-dire des erreurs qui sont consignées uniquement au maximum de journalisation, mais qui ne sont pas à l’origine du problème. Nous vous recommandons également de ne pas activer la journalisation des diagnostics de façon permanente. Utilisez-le uniquement lors du dépannage.



</div>

Dans chaque journal de l’observateur d’événements, Lync Server 2013 enregistre les événements d’informations, d’avertissement et d’erreur. Surveillez attentivement ces journaux pour suivre les types de transactions effectuées sur les serveurs Lync Server 2013. Vous devez archiver les journaux périodiquement ou utiliser la substitution automatique pour éviter la saturation de l'espace. Étant donné que les fichiers journaux peuvent occuper une quantité d’espace déterminée, augmentez la taille du journal (par exemple, à 50 Mo) et définissez-le sur Overwrite afin que le serveur Lync Server 2013 puisse continuer à écrire de nouveaux événements.

Vous pouvez également automatiser l’administration du journal des événements à l’aide des outils et technologies suivants :

  - System Center Operations Manager analyse l’intégrité et l’utilisation des serveurs Lync Server 2013. Lync Server 2013 Pack d’administration d’Operations Manager étend le gestionnaire des opérations en fournissant une surveillance spécialisée pour les serveurs qui exécutent Lync Server 2013.

  - Le pack d’administration Lync Server 2013 pour Operations Manager surveille les éditions standard et Enterprise de Lync Server 2013. Cette version intègre également le pack d’administration qualité de l’expérience (QoE), qui était auparavant un pack d’administration distinct.

Les types surveillés sont les entrées du journal des événements, les compteurs de performances et la surveillance avec état de QoE. Cette version du pack d’administration analyse uniquement Lync Server 2013 et 2010, et ne peut pas être utilisée pour surveiller Office Communications Server 2007.

Le pack d’administration offre les fonctionnalités suivantes :

  - Alertes indiquant le service qui affecte des événements

  - Alertes indiquant la configuration et d’autres problèmes liés à l’impact du service hors service

  - Analyse d’état des services Lync Server

  - Connaissances du produit : cause et résolution des problèmes identifiés

Pour plus d’informations sur le pack d’administration Lync Server 2013, consultez la rubrique [Monitoring Lync server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).

**Peigne**   d’événements l’outil peigne d’événements collecte des événements spécifiques dans les journaux des événements de plusieurs ordinateurs à un emplacement central. Il vous permet de signaler uniquement les ID d’événement ou les sources d’événements qu’il spécifie. Pour plus d’informations sur le peigne d’événements, voir le site Web sur les [outils de verrouillage et de gestion](https://go.microsoft.com/fwlink/?linkid=35607) .

**Déclencheurs d’événements**   dans Windows Server 2012 vous pouvez « joindre une tâche à cet événement » dans l’observateur d’événements Windows, où un administrateur peut exécuter un programme, envoyer un message électronique ou afficher un message à l’écran. Pour plus d’informations sur cette fonctionnalité, voir la rubrique Windows Server 2008 R2 [exécuter une tâche en réponse à un événement donné](https://technet.microsoft.com/library/cc748900.aspx). Vous pouvez également utiliser des outils de ligne de commande tels que « EventTrigger. exe » pour créer et interroger des journaux d’événements et associer des programmes à des événements journalisés particuliers. À l’aide de Eventtriggers. exe, vous pouvez créer des déclencheurs d’événements qui exécutent des programmes lorsque des événements spécifiques se produisent.

<div>

## <a name="see-also"></a>Voir aussi


[Observateur d’événements Windows](https://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

