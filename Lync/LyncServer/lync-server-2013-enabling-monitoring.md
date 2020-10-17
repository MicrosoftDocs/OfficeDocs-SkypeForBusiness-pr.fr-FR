---
title: 'Lync Server 2013 : activation de la surveillance'
description: 'Lync Server 2013 : activation de la surveillance.'
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
ms.openlocfilehash: d8995042bdc9b121dc5253940104bb167567ddcc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558480"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>Activation de la surveillance dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Bien que les agents de collecte de données unifiées soient automatiquement installés et activés sur chaque serveur frontal, cela ne signifie pas que vous commencerez automatiquement à collecter les données d’analyse à l’installation de Microsoft Lync Server 2013. Auparavant, vous devez associer vos serveurs frontaux/pools frontaux à une base de données de surveillance et vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience au niveau de l’étendue globale et/ou de l’étendue du site.

Pour obtenir des instructions pas à pas sur l’Association de serveurs frontaux ou de pools frontaux à une base de données de surveillance, reportez-vous à la rubrique [Association d’un magasin de surveillance à un pool frontal dans Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) dans le Guide de déploiement. Ces associations créées et votre nouvelle topologie Lync Server publiée, vous ne pourrez toujours pas recueillir des données de surveillance. En effet, par défaut, les enregistrements des détails des appels et les données QoE sont désactivés lors de l’installation de Lync Server 2013.

Afin de pouvoir commencer la collecte de données, vous devez activer la surveillance des enregistrements des détails des appels et/ou la surveillance des données de qualité de l’expérience. (Notez que vous n’avez pas besoin d’activer à la fois le contrôle d’enregistrement des détails des appels et la surveillance QoE ; si vous le souhaitez, vous pouvez activer un type de surveillance tout en laissant l’autre type désactivé.) Pour activer la surveillance des enregistrements des détails des appels au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Vous pouvez également activer la surveillance des enregistrements des détails des appels à partir du panneau de configuration Lync Server 2013. Dans le panneau de configuration Lync Server, procédez comme suit :

1.  Cliquez sur **Surveillance**.

2.  Sous l’onglet **Enregistrement des détails des appels**, double-cliquez sur le paramètre **Global**.

3.  Dans le volet **Paramètre de l’enregistrement des détails des appels (CDR)**, sélectionnez **Activer la surveillance des enregistrements des détails des appels**, puis cliquez sur **Valider**.

Pour activer la surveillance QoE au niveau global, exécutez la commande suivante à partir de Lync Server Management Shell :

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Si vous préférez, vous pouvez également activer la surveillance QoE depuis le panneau de configuration Lync Server. Dans le Panneau de configuration, effectuez la procédure suivante :

1.  Cliquez sur **Surveillance**.

2.  Sous l’onglet **Données de qualité de l’expérience**, double-cliquez sur le paramètre **Global**.

3.  Dans le volet **Paramètre de qualité de l’expérience (QoE)**, sélectionnez **Activer la surveillance des données de qualité de l’expérience**, puis cliquez sur **Valider**.

Comme indiqué, les exemples précédents activent la surveillance au niveau de l’étendue globale ; ils activent les surveillances CDR et QoE dans toute votre organisation. Vous pouvez également créer des paramètres de configuration CDR et QoE distincts au niveau de l’étendue du site, puis activer ou désactiver de façon sélective la surveillance pour chaque site. Par exemple, vous pouvez activer la surveillance CDR pour votre site de Redmond et la désactiver pour votre site de Dublin. Pour plus d’informations sur la gestion des paramètres de configuration de l’analyse, voir la rubrique relative à la [Configuration des paramètres d’enregistrement des détails des appels et de la qualité de l’expérience dans Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

