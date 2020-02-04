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
ms.openlocfilehash: 3023741b1b9e71d7789857c9b55fb195453ee5b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="05def-102">Paramètres de stratégie de groupe pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05def-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05def-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="05def-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="05def-104">Dans les versions précédentes de Lync et Office Communicator, un modèle d’administration de Communicator. adm autonome était disponible pour la configuration des paramètres de stratégie de groupe client.</span><span class="sxs-lookup"><span data-stu-id="05def-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="05def-105">Pour Lync 2013, les nouveaux fichiers de modèles d’administration (fichiers. admx et. adml) sont inclus avec le modèle d’administration de stratégie de groupe Office.</span><span class="sxs-lookup"><span data-stu-id="05def-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="05def-106">La disponibilité des fichiers. admx et. adml de 2013 Lync vous permet de télécharger des modèles et de gérer de façon centralisée des paramètres de stratégie de groupe pour tous vos programmes Office et modules linguistiques.</span><span class="sxs-lookup"><span data-stu-id="05def-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="05def-107">Pour plus d’informations, reportez-vous à la section « fichiers de modèles d’administration Office 2013 ( <http://go.microsoft.com/fwlink/p/?linkid=267516>ADMX, ADML) » dans la documentation Office 2013 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="05def-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="05def-108">Stratégies d’amorçage client</span><span class="sxs-lookup"><span data-stu-id="05def-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="05def-109">Il existe plusieurs stratégies de démarrage de client que vous devez configurer avant que les utilisateurs se connectent au serveur pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="05def-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="05def-110">Dans la mesure où ces stratégies entreront en vigueur avant que le client ne se connecte et ne commence à recevoir des paramètres de mise en service intrabande à partir du serveur, vous pouvez utiliser une stratégie de groupe pour les configurer.</span><span class="sxs-lookup"><span data-stu-id="05def-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="05def-111">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de démarrage de clients dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="05def-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

