---
title: Déployer les clients Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d42b410765b4cf8b7a52221f76ba532347ee3ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503001"
---
# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="0eab1-102">Déployer les clients Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0eab1-102">Deploy Lync Server 2013 clients</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eab1-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0eab1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0eab1-104">Après avoir migré les utilisateurs vers Lync Server 2013, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0eab1-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="0eab1-105">Utilisez le filtre de version du client sur le nouveau serveur Lync Server 2013 pour autoriser uniquement les clients sur lesquels les mises à jour les plus récentes sont installées pour se connecter.</span><span class="sxs-lookup"><span data-stu-id="0eab1-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="0eab1-106">Si nécessaire, configurez les paramètres de stratégie de groupe qui sont requises pour le démarrage du client.</span><span class="sxs-lookup"><span data-stu-id="0eab1-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="0eab1-107">Pour plus d’informations, reportez-vous à la rubrique [Configuring Client Bootstrapper Policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0eab1-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="0eab1-108">La configuration de ces paramètres est nécessaire seulement si vous voulez définir des nouvelles stratégies de démarrage du client.</span><span class="sxs-lookup"><span data-stu-id="0eab1-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="0eab1-109">Si vous ne prévoyez pas de configurer des stratégies de démarrage du client ou si vous voulez que les stratégies de démarrage du client héritées restent en vigueur, aucune action n’est alors requise.</span><span class="sxs-lookup"><span data-stu-id="0eab1-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="0eab1-110">Configurez d’autres stratégies utilisateur et client pour des utilisateurs ou des groupes d’utilisateurs spécifiques à l’aide du panneau de configuration Lync Server 2013, de l’environnement de gestion de Lync Server 2013 ou des deux.</span><span class="sxs-lookup"><span data-stu-id="0eab1-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="0eab1-111">Pour plus d’informations, reportez-vous aux [paramètres nouveaux et modifiés pour Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0eab1-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="0eab1-112">Déployez la dernière version des clients Lync Server 2013 avec les mises à jour cumulatives les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="0eab1-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="0eab1-113">Pour plus d’informations, voir [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0eab1-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="0eab1-114">Module Si votre organisation requiert le mode de confidentialité Enhanced presence de Lync Server 2013, une fois la migration terminée, définissez une règle de stratégie de version de client pour empêcher les versions antérieures du client de se connecter.</span><span class="sxs-lookup"><span data-stu-id="0eab1-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="0eab1-115">Activez ensuite le mode de confidentialité améliorée de la présence.</span><span class="sxs-lookup"><span data-stu-id="0eab1-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0eab1-116">N’activez pas le mode de confidentialité Enhanced presence de Lync 2013 tant que tous les utilisateurs d’un pool de serveurs donné n’ont pas installé les versions de client les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="0eab1-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

