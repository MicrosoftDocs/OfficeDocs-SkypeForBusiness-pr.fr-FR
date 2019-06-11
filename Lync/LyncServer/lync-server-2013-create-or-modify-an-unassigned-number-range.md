---
title: 'Lync Server 2013: création ou modification d’une plage de numéros non attribués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88c24e1f76e6c07e1a5e32b075aec6aa7de23ea1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="e62c3-102">Créer ou modifier une plage de nombres non affectées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e62c3-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e62c3-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e62c3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e62c3-104">Utilisez l’une des procédures suivantes pour configurer des plages de nombres non affectées pour l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="e62c3-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e62c3-105">Avant de configurer la table des numéros non attribués, vous devez déjà avoir défini une ou plusieurs annonces ou configurer un standard automatique de messagerie unifiée (MU).</span><span class="sxs-lookup"><span data-stu-id="e62c3-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e62c3-106">Pour utiliser le panneau de configuration de Lync Server pour configurer les numéros de téléphone non affectés</span><span class="sxs-lookup"><span data-stu-id="e62c3-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e62c3-107">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="e62c3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="e62c3-108">Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e62c3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e62c3-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e62c3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e62c3-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e62c3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e62c3-111">Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="e62c3-112">Dans la page **Numéro non attribué**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e62c3-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e62c3-p103">Pour créer une nouvelle plage de numéros, cliquez sur **Nouveau**. Dans **Nom**, tapez le nom de cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="e62c3-p103">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e62c3-115">Une fois que vous avez validé la nouvelle plage de numéros non attribués dans la base de données, vous ne pouvez plus modifier ce nom.</span><span class="sxs-lookup"><span data-stu-id="e62c3-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="e62c3-p104">Pour modifier une plage de numéros existante, tapez tout ou une partie du nom de la plage de numéros dans le champ de recherche. Dans la liste des plages de numéros résultante, cliquez sur celle voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-p104">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e62c3-118">Dans le premier champ **Plage de numéros**, tapez le numéro de début de plage, puis dans le second champ **Plage de numéros**, tapez le numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="e62c3-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="e62c3-119">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="e62c3-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e62c3-120">Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</span><span class="sxs-lookup"><span data-stu-id="e62c3-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e62c3-121">Le numéro doit correspondre à l’expression régulière (tel:)? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="e62c3-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="e62c3-122">Cela implique que le numéro peut commencer par la chaîne tel: (si vous ne spécifiez pas cette chaîne, elle sera automatiquement ajoutée pour vous), un signe plus (+) et un chiffre de 1 à 9.</span><span class="sxs-lookup"><span data-stu-id="e62c3-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="e62c3-123">Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="e62c3-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="e62c3-124">Dans **Service d’annonce**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e62c3-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="e62c3-125">Cliquez sur **Annonce**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="e62c3-126">Cliquez sur **Messagerie unifiée Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="e62c3-127">Si, dans l’étape précédente, vous avez cliqué sur **Annonce**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e62c3-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="e62c3-128">Sous **nom de domaine complet du serveur de destination**, cliquez sur **Sélectionner**, sur l’ID du service d’application exécutant l’application d’annonce qui traitera les appels entrants de cette plage de numéros non attribués, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="e62c3-129">Dans **Annonce**, cliquez sur l’annonce à associer à cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="e62c3-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="e62c3-130">Si, dans l’étape précédente, vous avez cliqué sur **Messagerie unifiée Exchange**, sous **Numéro de téléphone du standard automatique**, cliquez sur **Sélectionner**, puis sur le numéro de téléphone devant être utilisé par cette plage de numéros non attribués et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="e62c3-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-131">Click **OK**.</span></span>

10. <span data-ttu-id="e62c3-p106">Dans la page **Numéro non attribué**, vérifiez que les plages de numéros non attribués s’affichent dans l’ordre voulu. Pour déplacer une plage dans la table, cliquez sur un ou plusieurs noms consécutifs dans la liste de plages, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="e62c3-p106">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e62c3-134">Lync Server effectue une recherche dans la table des numéros non attribués de haut en bas, et utilise la première plage qui correspond au numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="e62c3-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="e62c3-135">Si des plages se chevauchent et qu’une plage spécifie une action de dernier recours, vérifiez qu’elle se trouve en bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="e62c3-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="e62c3-136">Une fois que vous disposez des plages de numéros non attribués dans l’ordre souhaité, cliquez sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="e62c3-137">Pour utiliser Windows PowerShell afin de configurer les numéros de téléphone non affectés</span><span class="sxs-lookup"><span data-stu-id="e62c3-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="e62c3-138">Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires, comme décrit dans la rubrique [autorisations de configuration du délégué dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e62c3-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="e62c3-139">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e62c3-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e62c3-140">Utilisez **New-CsUnassignedNumber** pour créer une plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="e62c3-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="e62c3-141">Utilisez **Set-CsUnassignedNumber** pour modifier une plage de numéros non attribués existante.</span><span class="sxs-lookup"><span data-stu-id="e62c3-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e62c3-p109">Si des plages se chevauchent et vous souhaitez qu’elles soient appliquées dans un ordre spécifique, incluez le paramètre Priority. La plage dont la priorité est la plus élevée sera appliquée à l’appel.</span><span class="sxs-lookup"><span data-stu-id="e62c3-p109">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="e62c3-144">Dans la ligne de commande, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e62c3-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="e62c3-145">Pour créer une plage de numéros pour un service Annonces, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e62c3-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="e62c3-146">Ou pour créer une plage de numéros pour le standard automatique de messagerie unifiée Exchange, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e62c3-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="e62c3-147">Exemple :</span><span class="sxs-lookup"><span data-stu-id="e62c3-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="e62c3-148">Ou</span><span class="sxs-lookup"><span data-stu-id="e62c3-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="e62c3-149">L’exemple suivant montre comment modifier les numéros d’une plage de numéros non attribués existante :</span><span class="sxs-lookup"><span data-stu-id="e62c3-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e62c3-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e62c3-150">See Also</span></span>


[<span data-ttu-id="e62c3-151">Supprimer une plage de numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e62c3-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="e62c3-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e62c3-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="e62c3-153">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e62c3-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="e62c3-154">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="e62c3-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

