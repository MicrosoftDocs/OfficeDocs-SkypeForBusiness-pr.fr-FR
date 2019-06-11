---
title: 'Lync Server 2013: paramètres de stratégie de groupe pour Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a>Paramètres de stratégie de groupe pour Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-03_

Dans les versions précédentes de Lync et Office Communicator, un modèle d’administration de Communicator. adm autonome était disponible pour la configuration des paramètres de stratégie de groupe client. Pour Lync 2013, les nouveaux fichiers de modèles d’administration (fichiers. admx et. adml) sont inclus avec le modèle d’administration de stratégie de groupe Office. La disponibilité des fichiers. admx et. adml de 2013 Lync vous permet de télécharger des modèles et de gérer de façon centralisée des paramètres de stratégie de groupe pour tous vos programmes Office et modules linguistiques. Pour plus d’informations, reportez-vous à la section «fichiers de modèles d’administration Office 2013 ( <http://go.microsoft.com/fwlink/p/?linkid=267516>ADMX, ADML)» dans la documentation Office 2013 à l’adresse.

<div>

## <a name="client-bootstrapping-policies"></a>Stratégies d’amorçage client

Il existe plusieurs stratégies de démarrage de client que vous devez configurer avant que les utilisateurs se connectent au serveur pour la première fois. Dans la mesure où ces stratégies entreront en vigueur avant que le client ne se connecte et ne commence à recevoir des paramètres de mise en service intrabande à partir du serveur, vous pouvez utiliser une stratégie de groupe pour les configurer. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de démarrage de clients dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

