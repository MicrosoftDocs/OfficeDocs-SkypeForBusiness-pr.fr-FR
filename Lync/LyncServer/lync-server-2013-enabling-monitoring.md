---
title: 'Lync Server 2013 : activation de la surveillance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f11aab3c58a43ac0746cb1f297bf4f3f85d28c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Activation de l’analyse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Bien que les agents de collecte des données unifiées soient automatiquement installés et activés sur chaque serveur frontal, cela signifie que vous commencerez automatiquement à collecter des données d’analyse dès que vous avez terminé d’installer Microsoft Lync Server 2013. À la place, vous devez effectuer les deux actions suivantes : vous devez associer votre serveur frontal/les listes frontales à une base de données de surveillance, et vous devez activer l’enregistrement des détails des appels (CDR) et/ou la qualité de l’expertise (QoE) sur l’étendue globale et/ou l’étendue du site.

Pour obtenir des instructions pas à pas sur l’utilisation d’un serveur frontal ou d’une base de données de surveillance, voir la rubrique [Association d’un magasin d’analyse avec un pool frontal dans Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) dans le Guide de déploiement. Une fois ces associations créées et après la publication de votre nouvelle topologie de serveur Lync, vous ne pourrez toujours pas collecter de données d’analyse. C’est pourquoi, par défaut, la collection de données CDR et QoE est désactivée lors de l’installation de Lync Server 2013.

Pour commencer la collecte de données, vous devez activer le contrôle CDR et/ou QoE. (Notez que vous n’avez pas besoin d’activer les contrôles CDR et QoE ; si vous le souhaitez, vous pouvez activer un seul type d’analyse tout en laissant l’autre type désactivé.) Pour activer le contrôle CDR dans l’étendue globale, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Vous pouvez également activer le contrôle de CDR à partir du panneau de configuration de Lync Server 2013. Dans le panneau de configuration de Lync Server, procédez comme suit :

1.  Cliquez sur **surveillance**.

2.  Dans l’onglet **enregistrement des détails des appels** , double-cliquez sur le paramètre **Global** .

3.  Dans le volet **modifier les paramètres d’enregistrement des détails des appels (CdR)** , sélectionnez **activer l’analyse de CDR** , puis cliquez sur **valider**.

Pour activer le contrôle QoE au niveau de l’étendue globale, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Si vous le souhaitez, vous pouvez également activer le contrôle QoE dans le panneau de configuration de Lync Server. Dans le panneau de configuration, procédez comme suit :

1.  Cliquez sur **surveillance**.

2.  Sous l’onglet **données de qualité de l’environnement** , double-cliquez sur le paramètre **Global** .

3.  Dans le volet des **paramètres de modification de la qualité de l’utilisation** , sélectionnez **activer l’analyse des données QoE** , puis cliquez sur **valider**.

Comme indiqué précédemment, les exemples précédents permettent de surveiller au niveau de l’étendue globale ; en d’autres, ils autorisent le contrôle CDR et QoE au sein de votre organisation. Vous pouvez également créer des paramètres de configuration de CDR et QoE séparés sur l’étendue du site, puis activer ou désactiver de manière sélective le contrôle de chaque site. Par exemple, vous pouvez activer le contrôle de CDR pour votre site de Redmond, mais désactiver le contrôle CDR pour votre site de Dublin. Pour plus d’informations sur la gestion de vos paramètres de configuration de la surveillance, voir le Guide de déploiement [Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’utilisation dans Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

