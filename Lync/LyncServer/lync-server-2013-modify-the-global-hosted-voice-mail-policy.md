---
title: 'Lync Server 2013 : modification de la stratégie de messagerie vocale hébergée dans le monde entier'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="e2d28-102">Modifier la stratégie globale de messagerie vocale hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2d28-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2d28-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e2d28-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e2d28-104">La stratégie de messagerie vocale *globale* hébergée est installée avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e2d28-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="e2d28-105">Vous pouvez le modifier en fonction de vos besoins, mais vous ne pouvez pas le renommer ou le supprimer.</span><span class="sxs-lookup"><span data-stu-id="e2d28-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="e2d28-106">Pour modifier la stratégie globale, vous devez utiliser l’applet de passe Set-CsHostedVoicemailPolicy pour définir les paramètres sur les valeurs appropriées pour votre déploiement spécifique.</span><span class="sxs-lookup"><span data-stu-id="e2d28-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="e2d28-107">Pour plus d’informations sur l’applet [de connexion Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e2d28-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="e2d28-108">Pour modifier la stratégie de messagerie vocale hébergée dans le monde</span><span class="sxs-lookup"><span data-stu-id="e2d28-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="e2d28-109">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e2d28-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e2d28-110">Exécutez l’applet de cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres de stratégie globale pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="e2d28-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="e2d28-111">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e2d28-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="e2d28-112">Étant donné que cette commande ne spécifie pas le paramètre Identity de la stratégie, l’interface de ligne de commande Windows PowerShell définit les valeurs suivantes sur la stratégie de messagerie vocale hébergée dans le monde entier :</span><span class="sxs-lookup"><span data-stu-id="e2d28-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="e2d28-113">**Destination** spécifie le nom de domaine complet (FQDN) du service Exchange um hébergé.</span><span class="sxs-lookup"><span data-stu-id="e2d28-113">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="e2d28-114">Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée et que la stratégie attribuée de l’utilisateur n’a pas de valeur de destination, l’activation échoue.</span><span class="sxs-lookup"><span data-stu-id="e2d28-114">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="e2d28-115">**Organization** spécifie une liste séparée par des virgules des clients Exchange que les utilisateurs du serveur principal de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2d28-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="e2d28-116">Chaque client doit être spécifié en tant que nom de domaine complet (FQDN) du client sur le service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="e2d28-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2d28-117">Dans l’applet de l’exemple précédent, la valeur « corp1.litwareinc.com » remplace une valeur éventuellement déjà présente dans le paramètre Organization.</span><span class="sxs-lookup"><span data-stu-id="e2d28-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="e2d28-118">Par exemple, si la stratégie comporte déjà une liste d’organisations séparée par des virgules, la liste complète serait remplacée.</span><span class="sxs-lookup"><span data-stu-id="e2d28-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="e2d28-119">Si vous souhaitez ajouter une organisation à la liste au lieu de remplacer la liste entière, exécutez une commande similaire à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="e2d28-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

