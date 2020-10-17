---
title: 'Lync Server 2013 : configuration des paramètres de parcage d’appel'
description: 'Lync Server 2013 : configurer les paramètres de parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8862208a68c89151096349508a4c849a5649b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546640"
---
# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="4bfc0-103">Configurer les paramètres de parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bfc0-103">Configure Call Park settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bfc0-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4bfc0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4bfc0-105">Si vous ne souhaitez pas utiliser les paramètres de parcage d’appel par défaut, vous pouvez les personnaliser.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="4bfc0-106">Lorsque vous installez l’application de parcage d’appel, les paramètres globaux sont configurés par défaut.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="4bfc0-107">Vous pouvez modifier les paramètres globaux et définir également des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="4bfc0-108">L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="4bfc0-109">L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bfc0-110">Nous vous recommandons de configurer au moins l’option <STRONG>OnTimeoutURI</STRONG> pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-110">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="4bfc0-111">Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="4bfc0-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bfc0-112">Cette option :</span><span class="sxs-lookup"><span data-stu-id="4bfc0-112">This option:</span></span></th>
<th><span data-ttu-id="4bfc0-113">Définit ceci :</span><span class="sxs-lookup"><span data-stu-id="4bfc0-113">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bfc0-114"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="4bfc0-114"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="4bfc0-115">Laps de temps qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="4bfc0-p102">La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale est de 10 minutes. La valeur par défaut est 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bfc0-119"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="4bfc0-119"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="4bfc0-120">Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-120">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="4bfc0-p103">Les valeurs sont True ou False. La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bfc0-123"><strong>Valeur maxcallpickupattempts</strong></span><span class="sxs-lookup"><span data-stu-id="4bfc0-123"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="4bfc0-p104">Nombre de sonnerie de rappel d’un appel parqué avant qu’il ne soit transféré vers l’URI de remplacement spécifié pour le paramètre <strong>OnTimeoutURI</strong>. La valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bfc0-126"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="4bfc0-126"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="4bfc0-127">Adresse SIP de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur <strong>MaxCallPickupAttempts</strong> est atteinte.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-127">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="4bfc0-p105">La valeur doit être une URI SIP et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="4bfc0-131">Pour configurer les paramètres de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="4bfc0-131">To configure Call Park settings</span></span>

1.  <span data-ttu-id="4bfc0-132">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4bfc0-132">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4bfc0-133">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4bfc0-134">Générer</span><span class="sxs-lookup"><span data-stu-id="4bfc0-134">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="4bfc0-135">L’applet de commande <STRONG>Get-CsSite</STRONG> permet d’identifier le site.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-135">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="4bfc0-136">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4bfc0-136">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="4bfc0-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4bfc0-137">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bfc0-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bfc0-138">See Also</span></span>


[<span data-ttu-id="4bfc0-139">Personnalisation de l’attente musicale du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bfc0-139">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="4bfc0-140">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4bfc0-140">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="4bfc0-141">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="4bfc0-141">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="4bfc0-142">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="4bfc0-142">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

