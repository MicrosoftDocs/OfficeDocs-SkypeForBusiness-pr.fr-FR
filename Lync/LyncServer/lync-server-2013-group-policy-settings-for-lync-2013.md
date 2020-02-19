---
title: 'Lync Server 2013 : paramètres de stratégie de groupe pour Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cae5fdb813f7f58889dd1305b117f0e07ff294e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Paramètres de stratégie de groupe pour Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Dans les versions précédentes de Lync et Office Communicator, un modèle d’administration de Communicator. adm autonome était disponible pour la configuration des paramètres de stratégie de groupe client. Pour Lync 2013, les nouveaux fichiers de modèle d’administration (fichiers. admx et. adml) sont inclus avec le modèle d’administration de stratégie de groupe Office. La disponibilité des fichiers Lync 2013. admx et. adml vous permet de télécharger des modèles et de gérer les paramètres de stratégie de groupe de manière centralisée pour tous vos programmes et modules linguistiques Office. Pour plus d’informations, reportez-vous à la rubrique « Office 2013 administrative Template Files (ADMX, <https://go.microsoft.com/fwlink/p/?linkid=267516>adml) » dans la documentation Office 2013 à l’adresse.

<div>

## <a name="client-bootstrapping-policies"></a>Stratégies de démarrage du client

Vous devez configurer plusieurs stratégies de démarrage du client pour permettre aux utilisateurs de se connecter au serveur pour la première fois. Dans la mesure où ces stratégies sont appliquées avant que le client ne se connecte et commence à recevoir les paramètres de mise en service intrabande de la part du serveur, vous pouvez utiliser la stratégie de groupe pour les configurer. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de démarrage client dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

