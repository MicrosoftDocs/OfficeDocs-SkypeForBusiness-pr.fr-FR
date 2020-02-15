---
title: 'Lync Server 2013 : modifier la stratégie de messagerie vocale hébergée globale'
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
ms.openlocfilehash: 1746f622afb380f53a0109400a7d326b0b3c5de7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="4fb45-102">Modifier la stratégie de messagerie vocale hébergée globale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fb45-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fb45-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="4fb45-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="4fb45-104">La stratégie de messagerie vocale *globale* hébergée est installée avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4fb45-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="4fb45-105">Vous pouvez la modifier en fonction de vos besoins, mais pas la renommer ni la supprimer.</span><span class="sxs-lookup"><span data-stu-id="4fb45-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="4fb45-106">Pour modifier la stratégie globale, utilisez la cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres sur les valeurs appropriées pour votre déploiement spécifique.</span><span class="sxs-lookup"><span data-stu-id="4fb45-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="4fb45-107">Pour plus d’informations sur la cmdlet [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) , voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4fb45-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="4fb45-108">Pour modifier la stratégie de messagerie vocale hébergée globale</span><span class="sxs-lookup"><span data-stu-id="4fb45-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="4fb45-109">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4fb45-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4fb45-110">Exécutez la cmdlet Set-CsHostedVoicemailPolicy pour définir les paramètres de stratégie globale pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="4fb45-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="4fb45-111">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="4fb45-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="4fb45-112">Étant donné que cette commande ne spécifie pas le paramètre Identity de la stratégie, l’interface de ligne de commande Windows PowerShell définit les valeurs suivantes sur la stratégie de messagerie vocale globale hébergée :</span><span class="sxs-lookup"><span data-stu-id="4fb45-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="4fb45-p103">**Destination** spécifie le nom de domaine complet du service de messagerie unifiée Exchange hébergé. Ce paramètre est facultatif, mais si vous tentez d’activer un utilisateur pour la messagerie vocale hébergée alors que la stratégie affectée à l’utilisateur n’a pas de valeur Destination, l’activation échoue.</span><span class="sxs-lookup"><span data-stu-id="4fb45-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="4fb45-115">**Organisation** spécifie une liste séparée par des virgules des clients Exchange hébergeant des utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4fb45-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="4fb45-116">Chaque locataire doit être spécifié avec son nom de domaine complet (FQDN) dans le service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="4fb45-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fb45-117">Dans l’exemple de cmdlet précédent, la valeur « corp1.litwareinc.com » remplace toute valeur qui pourrait déjà figurer dans le paramètre Organization.</span><span class="sxs-lookup"><span data-stu-id="4fb45-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="4fb45-118">Par exemple, si la stratégie contient déjà une liste d’organisations séparées par des virgules, la liste complète serait remplacée.</span><span class="sxs-lookup"><span data-stu-id="4fb45-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="4fb45-119">Si vous souhaitez ajouter une organisation à la liste au lieu de remplacer toute la liste, exécutez une commande semblable à la suivante.</span><span class="sxs-lookup"><span data-stu-id="4fb45-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
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

