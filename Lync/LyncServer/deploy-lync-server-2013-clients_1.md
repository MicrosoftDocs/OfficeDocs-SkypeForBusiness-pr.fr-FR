---
title: Déploiement de clients Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="202b4-102">Déploiement de clients Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="202b4-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="202b4-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="202b4-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="202b4-104">Après avoir migré des utilisateurs vers Lync Server 2013, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="202b4-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="202b4-105">Utilisez le filtre de version du client sur le nouveau serveur Lync Server 2013 pour autoriser uniquement les clients sur lesquels les mises à jour les plus récentes sont installées pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="202b4-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="202b4-106">Le cas échéant, configurez les paramètres de stratégie de groupe requis pour le démarrage du client.</span><span class="sxs-lookup"><span data-stu-id="202b4-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="202b4-107">Pour plus d’informations, reportez-vous à la rubrique [configuration de stratégies d’amorçage client dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="202b4-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="202b4-108">La configuration de ces paramètres n’est nécessaire que si vous voulez modifier les stratégies d’amorçage client existantes ou si vous voulez définir de nouvelles stratégies de démarrage de client.</span><span class="sxs-lookup"><span data-stu-id="202b4-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="202b4-109">Si vous n’envisagez pas de configurer des stratégies d’amorçage client ou si vous souhaitez que les stratégies d’amorçage de clients héritées restent en vigueur, aucune action n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="202b4-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="202b4-110">Configurez d’autres stratégies utilisateur et client pour des utilisateurs ou des groupes d’utilisateurs spécifiques à l’aide du panneau de configuration de Lync Server 2013, de Lync Server 2013 Management Shell, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="202b4-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="202b4-111">Pour plus d’informations, reportez-vous aux [paramètres nouveaux et modifiés pour Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="202b4-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="202b4-112">Déployez la dernière version de clients 2013 Lync Server avec les mises à jour les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="202b4-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="202b4-113">Pour plus d’informations, reportez-vous à la section [déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="202b4-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="202b4-114">Facultatif Si votre organisation nécessite le mode de confidentialité de présence Enhanced de Lync Server 2013, une fois la migration terminée, définissez une règle de stratégie de version de client pour empêcher les versions de client antérieure de se connecter.</span><span class="sxs-lookup"><span data-stu-id="202b4-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="202b4-115">Activez ensuite le mode de confidentialité Enhanced Presence.</span><span class="sxs-lookup"><span data-stu-id="202b4-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="202b4-116">N’activez pas le mode de confidentialité de la présence améliorée de Lync 2013 tant que tous les utilisateurs sur un pool de serveurs donné n’ont pas installé la version la plus récente du client.</span><span class="sxs-lookup"><span data-stu-id="202b4-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

