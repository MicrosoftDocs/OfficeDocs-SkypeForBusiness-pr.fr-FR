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
ms.openlocfilehash: ba88fdce88280597e9e621c13267de2b9b76d0fb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="fc5c9-102">Paramètres de stratégie de groupe pour Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fc5c9-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc5c9-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fc5c9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fc5c9-104">Dans les versions précédentes de Lync et Office Communicator, un modèle d’administration de Communicator. adm autonome était disponible pour la configuration des paramètres de stratégie de groupe client.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="fc5c9-105">Pour Lync 2013, les nouveaux fichiers de modèle d’administration (fichiers. admx et. adml) sont inclus avec le modèle d’administration de stratégie de groupe Office.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="fc5c9-106">La disponibilité des fichiers Lync 2013. admx et. adml vous permet de télécharger des modèles et de gérer les paramètres de stratégie de groupe de manière centralisée pour tous vos programmes et modules linguistiques Office.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="fc5c9-107">Pour plus d’informations, reportez-vous à la rubrique « Office 2013 administrative Template Files (ADMX, <http://go.microsoft.com/fwlink/p/?linkid=267516>adml) » dans la documentation Office 2013 à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="fc5c9-108">Stratégies de démarrage du client</span><span class="sxs-lookup"><span data-stu-id="fc5c9-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="fc5c9-109">Vous devez configurer plusieurs stratégies de démarrage du client pour permettre aux utilisateurs de se connecter au serveur pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="fc5c9-110">Dans la mesure où ces stratégies sont appliquées avant que le client ne se connecte et commence à recevoir les paramètres de mise en service intrabande de la part du serveur, vous pouvez utiliser la stratégie de groupe pour les configurer.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="fc5c9-111">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies de démarrage client dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="fc5c9-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

