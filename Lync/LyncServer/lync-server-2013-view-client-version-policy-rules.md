---
title: 'Lync Server 2013 : afficher les règles de stratégie de version du client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 480e3002c6c6a22564c23bf4225d49cbd044f3c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="cce8e-102">Afficher les règles de stratégie de version des clients dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cce8e-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cce8e-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cce8e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cce8e-104">Une stratégie de version de client est composée d’un ensemble de règles de stratégie de version de client.</span><span class="sxs-lookup"><span data-stu-id="cce8e-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="cce8e-105">Ces règles définissent les actions à effectuer lorsque les utilisateurs tentent de se connecter avec des clients et des versions de client spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cce8e-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="cce8e-106">Vous pouvez afficher les règles de stratégie de version des clients à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cce8e-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="cce8e-107">Pour afficher les règles de stratégie de version des clients à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="cce8e-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cce8e-108">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cce8e-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cce8e-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cce8e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cce8e-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cce8e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cce8e-111">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **stratégie de version du client** .</span><span class="sxs-lookup"><span data-stu-id="cce8e-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="cce8e-112">Sur la page **stratégie de version du client** , double-cliquez sur une stratégie de version de client que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="cce8e-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="cce8e-113">Les règles s’affichent dans la page **modifier la stratégie de version du client** .</span><span class="sxs-lookup"><span data-stu-id="cce8e-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="cce8e-114">Pour afficher les détails d’une règle, sélectionnez-la, puis cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cce8e-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cce8e-115">Affichage des règles de stratégie de version des clients à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cce8e-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cce8e-116">Vous pouvez afficher les règles de stratégie de version des clients à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsClientVersionPolicyRule** .</span><span class="sxs-lookup"><span data-stu-id="cce8e-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="cce8e-117">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cce8e-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cce8e-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cce8e-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="cce8e-119">Pour afficher les règles de stratégie de version des clients</span><span class="sxs-lookup"><span data-stu-id="cce8e-119">To view client version policy rules</span></span>

  - <span data-ttu-id="cce8e-120">Pour afficher les règles de stratégie de version des clients, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="cce8e-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="cce8e-121">Cela renverra des informations similaires à celles-ci pour chaque règle configurée :</span><span class="sxs-lookup"><span data-stu-id="cce8e-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="cce8e-122">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="cce8e-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

