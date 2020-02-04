---
title: 'Lync Server 2013 : configurer les paramètres de parc d’appels'
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
ms.openlocfilehash: ee4f12ccf614816e27262f8b393cdc1dac4a7a5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="75400-102">Configurer les paramètres de parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75400-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75400-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="75400-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="75400-104">Si vous ne voulez pas utiliser les paramètres de parc d’appels par défaut, vous pouvez les personnaliser.</span><span class="sxs-lookup"><span data-stu-id="75400-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="75400-105">Lorsque vous installez l’application de parc d’appels, les paramètres globaux sont configurés par défaut.</span><span class="sxs-lookup"><span data-stu-id="75400-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="75400-106">Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="75400-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="75400-107">L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="75400-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="75400-108">L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="75400-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75400-109">Nous vous recommandons de configurer au moins l’option <STRONG>OnTimeoutURI</STRONG> pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.</span><span class="sxs-lookup"><span data-stu-id="75400-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="75400-110">Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="75400-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75400-111">Cette option :</span><span class="sxs-lookup"><span data-stu-id="75400-111">This option:</span></span></th>
<th><span data-ttu-id="75400-112">Spécifie cet élément :</span><span class="sxs-lookup"><span data-stu-id="75400-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75400-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="75400-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="75400-114">Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</span><span class="sxs-lookup"><span data-stu-id="75400-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="75400-p102">La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="75400-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75400-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="75400-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="75400-119">Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="75400-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="75400-p103">Les valeurs sont True ou False. La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="75400-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75400-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="75400-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="75400-p104">Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre <strong>OnTimeoutURI</strong>. La valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="75400-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75400-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="75400-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="75400-126">Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur <strong>MaxCallPickupAttempts</strong> est atteinte.</span><span class="sxs-lookup"><span data-stu-id="75400-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="75400-p105">La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</span><span class="sxs-lookup"><span data-stu-id="75400-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="75400-130">Pour configurer les paramètres du parc d’appels</span><span class="sxs-lookup"><span data-stu-id="75400-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="75400-131">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="75400-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="75400-132">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="75400-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="75400-133">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="75400-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="75400-134">L’applet de commande <STRONG>Get-CsSite</STRONG> permet d’identifier le site.</span><span class="sxs-lookup"><span data-stu-id="75400-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="75400-135">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="75400-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="75400-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="75400-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75400-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="75400-137">See Also</span></span>


[<span data-ttu-id="75400-138">Personnaliser le parc d’appels en attente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75400-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="75400-139">Nouveau-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="75400-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="75400-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="75400-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="75400-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="75400-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

