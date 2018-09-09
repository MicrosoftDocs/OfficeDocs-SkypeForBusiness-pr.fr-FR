---
title: Créer ou modifier une plage de numéros non attribuée dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Créer, modifier ou supprimer des plages de numéros non attribués pour l’application d’annonce dans Skype pour Business Server Enterprise Voice. Cela affecte le traitement des appels à des numéros non attribués.
ms.openlocfilehash: 2acfa15ac6a5fdcdea2dc56fd74a067712875218
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886267"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="0ddc2-104">Créer ou modifier une plage de numéros non attribuée dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="0ddc2-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="0ddc2-105">Créer, modifier ou supprimer des plages de numéros non attribués pour l’application d’annonce dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="0ddc2-106">Cela affecte le traitement des appels à des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="0ddc2-107">Skype pour Business Server vous permet de dire que se passe-t-il pour les appels entrants aux numéros de téléphone qui sont valides pour votre organisation, mais ne sont pas affectés à un utilisateur ou un téléphone.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="0ddc2-108">Pour gérer ces appels, vous devez configurer une table de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="0ddc2-109">Vous pouvez utiliser la table pour acheminer les appels vers une application d’annonce ou à un serveur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="0ddc2-p104">La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec tous les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez modifier la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="0ddc2-116">Configuration des numéros de téléphone non attribués</span><span class="sxs-lookup"><span data-stu-id="0ddc2-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="0ddc2-117">Utilisez une des procédures suivantes pour configurer les plages de numéros non attribués pour l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ddc2-118">Avant de configurer la table des numéros non attribuée, votre système doit avoir défini des annonces ou configuré un standard automatique de messagerie unifiée Exchange (MU).</span><span class="sxs-lookup"><span data-stu-id="0ddc2-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0ddc2-119">Lorsqu’une personne appelle un numéro non attribué, Skype pour Business Server recherche dans la table des numéros non attribuée à partir du haut vers le bas et utilise la première plage correspondante.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="0ddc2-120">Par conséquent, une action que vous voulez voir effectuée en dernier ressort doit être spécifiée pour la dernière plage de la table.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="0ddc2-121">Utiliser Skype pour Business Server Control Panel pour configurer des numéros de téléphone non attribués</span><span class="sxs-lookup"><span data-stu-id="0ddc2-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="0ddc2-122">Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0ddc2-123">Pour plus d’informations, voir **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0ddc2-124">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0ddc2-125">Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="0ddc2-126">Dans la page **Numéro non attribué**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="0ddc2-p107">Pour créer une nouvelle plage de numéros, cliquez sur **Nouveau**. Dans **Nom**, tapez le nom de cette plage de numéros.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0ddc2-129">Une fois que vous avez validé la nouvelle plage de numéros non attribués dans la base de données, vous ne pouvez plus modifier ce nom.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="0ddc2-p108">Pour modifier une plage de numéros existante, tapez tout ou une partie du nom de la plage de numéros dans le champ de recherche. Dans la liste des plages de numéros résultante, cliquez sur celle voulue, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0ddc2-132">Dans le premier champ **Plage de numéros**, tapez le numéro de début de plage, puis dans le second champ **Plage de numéros**, tapez le numéro de fin de la plage.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="0ddc2-133">Le numéro de début de la plage doit être inférieur ou égal au numéro de fin de cette plage.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="0ddc2-134">Si le numéro de début ou de fin de plage inclut un numéro de poste, les numéros de début et de fin de plage doivent inclure un poste, et le numéro d’extension doit être le même pour les numéros de début et de fin de plage.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="0ddc2-135">Le numéro doit correspondre à l’expression régulière (Tél. :) ? (\+) ? [1-9] \d{0,17}( ; ext = [1-9] \d{0,9}) ?.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="0ddc2-136">Cela signifie que le nombre peut commencer par la chaîne tel : (si vous ne spécifiez pas cette chaîne, il est automatiquement ajouté pour vous), un signe plus (+) et un chiffre 1 à 9.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="0ddc2-137">Le numéro de téléphone peut comporter jusqu’à 17 chiffres et peut être suivi d’un poste au format ;ext= suivi du numéro de poste.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="0ddc2-138">Dans **Service d’annonce**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="0ddc2-139">Cliquez sur **Annonce**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="0ddc2-140">Cliquez sur **Messagerie unifiée Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="0ddc2-141">Si, dans l’étape précédente, vous avez cliqué sur **Annonce**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="0ddc2-142">a.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-142">a.</span></span> <span data-ttu-id="0ddc2-143">Sous **nom de domaine complet du serveur de destination**, cliquez sur **Sélectionner**, cliquez sur l’ID de service du service d’Application qui exécute l’application d’annonce qui gèrent les appels entrants à cette plage de numéros non attribués, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="0ddc2-144">b.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-144">b.</span></span> <span data-ttu-id="0ddc2-145">Dans **Annonce**, cliquez sur l’annonce à associer à cette plage de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="0ddc2-146">Si, dans l’étape précédente, vous avez cliqué sur **Messagerie unifiée Exchange**, sous **Numéro de téléphone du standard automatique**, cliquez sur **Sélectionner**, puis sur le numéro de téléphone devant être utilisé par cette plage de numéros non attribués et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="0ddc2-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="0ddc2-p112">Dans la page **Numéro non attribué**, vérifiez que les plages de numéros non attribués s’affichent dans l’ordre voulu. Pour déplacer une plage dans la table, cliquez sur un ou plusieurs noms consécutifs dans la liste de plages, puis cliquez sur la flèche vers le haut ou vers le bas.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0ddc2-150">Skype pour Business Server recherche dans la table des numéros non attribuée à partir du haut vers le bas et utilise la première plage qui correspond au numéro non attribué.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="0ddc2-151">Si des plages se chevauchent et qu’une plage spécifie une action de dernier recours, vérifiez qu’elle se trouve en bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="0ddc2-152">Une fois que vous disposez des plages de numéros non attribués dans l’ordre souhaité, cliquez sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="0ddc2-153">Utiliser Skype pour Business Server Management Shell pour configurer des numéros de téléphone non attribués</span><span class="sxs-lookup"><span data-stu-id="0ddc2-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="0ddc2-154">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0ddc2-155">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0ddc2-156">Utilisez la **Cmdlet New-CsUnassignedNumber** pour créer une nouvelle plage de numéros non attribuée.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="0ddc2-157">Utilisez **Set-CsUnassignedNumber** pour modifier une plage de numéros non attribuée existante.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0ddc2-p115">Si des plages se chevauchent et vous souhaitez qu’elles soient appliquées dans un ordre spécifique, incluez le paramètre Priority. La plage dont la priorité est la plus élevée sera appliquée à l’appel.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-p115">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span> 
  
    <span data-ttu-id="0ddc2-160">Dans la ligne de commande, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-160">At the command line, do one of the following:</span></span>
    
     - <span data-ttu-id="0ddc2-161">Pour créer une plage de numéros pour un service Annonces, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-161">To create a number range for an Announcement service, run:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="0ddc2-162">Ou pour créer une plage de numéros pour le standard automatique de messagerie unifiée Exchange, exécutez :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-162">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="0ddc2-163">Exemple :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-163">For example:</span></span>
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="0ddc2-164">Ou</span><span class="sxs-lookup"><span data-stu-id="0ddc2-164">Or</span></span>
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

    <span data-ttu-id="0ddc2-165">L’exemple suivant montre comment modifier les numéros d’une plage de numéros non attribués existante :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-165">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="0ddc2-166">Suppression d’une plage de numéros non attribués</span><span class="sxs-lookup"><span data-stu-id="0ddc2-166">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="0ddc2-167">Utiliser Skype pour Business Server Control Panel pour supprimer une plage de numéros non attribuée</span><span class="sxs-lookup"><span data-stu-id="0ddc2-167">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="0ddc2-168">Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-168">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0ddc2-169">Pour plus d’informations, voir **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-169">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0ddc2-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0ddc2-171">Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-171">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="0ddc2-172">Dans la page **Numéro non attribué**, dans le champ recherche, tapez entièrement ou partiellement le nom de la plage de numéros non attribués que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-172">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="0ddc2-173">Dans la liste des plages de numéros résultante, cliquez sur le nom, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-173">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="0ddc2-174">Cliquez sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-174">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="0ddc2-175">Utiliser Skype pour Business Server Management Shell pour supprimer une plage de numéros non attribuée</span><span class="sxs-lookup"><span data-stu-id="0ddc2-175">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="0ddc2-176">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires comme indiqué dans **Déléguer des autorisations d’installation**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-176">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0ddc2-177">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-177">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0ddc2-178">Dans la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-178">At the command line, type:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="0ddc2-179">Exemple :</span><span class="sxs-lookup"><span data-stu-id="0ddc2-179">For example:</span></span>
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="0ddc2-180">Pour plus d’informations sur d’autres options, voir [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0ddc2-180">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0ddc2-181">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ddc2-181">See also</span></span>

[<span data-ttu-id="0ddc2-182">Nouvelle-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="0ddc2-182">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="0ddc2-183">Set-CsUnassignedNumber.</span><span class="sxs-lookup"><span data-stu-id="0ddc2-183">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="0ddc2-184">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="0ddc2-184">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)