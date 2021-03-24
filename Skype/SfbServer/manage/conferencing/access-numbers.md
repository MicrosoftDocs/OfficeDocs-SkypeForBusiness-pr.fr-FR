---
title: 'Gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Résumé : Découvrez comment gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099150"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="abb07-103">Gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="abb07-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="abb07-104">**Résumé :** Découvrez comment gérer les numéros d’accès aux conférences téléphoniques dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abb07-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="abb07-p101">Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros apparaissent dans les invitations à une réunion et sur la page Web des paramètres de configuration des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="abb07-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="abb07-107">Cette rubrique décrit comment afficher, modifier ou supprimer des numéros d’accès aux conférences téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="abb07-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="abb07-108">Pour plus d’informations sur la création de numéros d’accès initiaux, voir [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="abb07-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="abb07-109">Afficher les numéros d’accès aux conférences téléphoniques</span><span class="sxs-lookup"><span data-stu-id="abb07-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="abb07-110">Vous pouvez afficher les numéros d’accès aux conférences téléphoniques à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="abb07-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="abb07-111">Afficher les numéros d’accès à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="abb07-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="abb07-112">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="abb07-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="abb07-113">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abb07-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="abb07-114">Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**</span><span class="sxs-lookup"><span data-stu-id="abb07-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="abb07-115">Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.</span><span class="sxs-lookup"><span data-stu-id="abb07-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="abb07-116">Dans **Modifier,** cochez **la case Afficher les détails.**</span><span class="sxs-lookup"><span data-stu-id="abb07-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="abb07-117">Afficher les numéros d’accès à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="abb07-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="abb07-118">Pour afficher des informations sur les numéros d’accès aux appels, utilisez l';cmdlet **Get-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="abb07-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="abb07-119">La commande suivante retourne une collection de tous les numéros d’accès aux conférences téléphoniques configurés pour être utilisés dans l’organisation :</span><span class="sxs-lookup"><span data-stu-id="abb07-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="abb07-120">Voici un exemple du type d’informations renvoyées :</span><span class="sxs-lookup"><span data-stu-id="abb07-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="abb07-121">Pour plus d’informations, [voir Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abb07-121">For more information, see [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="abb07-122">Modifier les numéros d’accès aux conférences téléphoniques</span><span class="sxs-lookup"><span data-stu-id="abb07-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="abb07-123">Vous pouvez modifier les numéros d’accès à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="abb07-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="abb07-124">Modifier les numéros d’accès à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="abb07-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="abb07-125">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="abb07-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="abb07-126">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abb07-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="abb07-127">Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**</span><span class="sxs-lookup"><span data-stu-id="abb07-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="abb07-128">Dans **la** page Numéro d’accès, cliquez sur l’un des numéros d’accès à la connexion dans la liste, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**</span><span class="sxs-lookup"><span data-stu-id="abb07-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="abb07-129">L’utilisation du champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès à la connexion risque de ne pas produire les résultats que vous attendez.</span><span class="sxs-lookup"><span data-stu-id="abb07-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="abb07-130">Au lieu de cela, tiez la liste par colonne d’intérêt pour identifier le numéro d’accès à la connexion que vous souhaitez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="abb07-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="abb07-131">Dans **le numéro d’affichage,** tapez le numéro de téléphone composé par les utilisateurs du réseau téléphonique commuté (PSTN) pour participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="abb07-132">Ce numéro s’affiche dans les invitations aux réunions et dans la page web Paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="abb07-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="abb07-133">Dans **nom d’affichage,** tapez une description pour le numéro d’accès à la connexion.</span><span class="sxs-lookup"><span data-stu-id="abb07-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="abb07-134">Il s’agit du nom associé au numéro d’accès à la connexion dans les résultats de recherche Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="abb07-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="abb07-135">Ce nom s’affiche dans le client lorsqu’un utilisateur appelle le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="abb07-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="abb07-136">Dans **l’URI** de ligne, tapez le numéro E.164 du numéro d’accès à la numérotation au format URI TEL, en incluant le symbole + avant le numéro et en excluant les espaces.</span><span class="sxs-lookup"><span data-stu-id="abb07-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="abb07-137">Par exemple, tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="abb07-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="abb07-138">Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès aux conférences téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="abb07-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="abb07-139">Dans **l’URI SIP,** faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="abb07-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="abb07-140">Dans la zone de texte, tapez un URI SIP unique pour ce numéro d’accès de conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="abb07-141">Cet URI SIP s’affiche à différents emplacements, y compris, mais sans s’y limiter, les messages de notification d’appel et les versions précédentes des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="abb07-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="abb07-142">Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès de conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="abb07-143">L’URI SIP ne peut pas être modifié après la création du numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="abb07-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="abb07-144">La seule façon de modifier l’URI SIP consiste à supprimer et recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="abb07-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="abb07-145">Dans la zone de liste liste, cliquez sur le domaine de l’application De l’Attendant de conférence qui prend en charge ce numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="abb07-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="abb07-146">Dans **Pool,** cliquez sur le pool qui exécute l’instance de l’Attendant de conférence qui prend en charge ce numéro d’accès à la conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="abb07-147">Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’cmdlet **Move-CsApplicationEndpoint** ou supprimer et recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="abb07-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="abb07-148">Dans **la langue principale,** cliquez sur la langue dans laquelle les invites sont lées pour ce numéro d’accès à la connexion.</span><span class="sxs-lookup"><span data-stu-id="abb07-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="abb07-149">La langue principale est celle que l’Attendant de conférence utilise pour répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="abb07-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="abb07-150">Les langues prise en charge sont affichées avec chaque numéro de téléphone d’accès sur la page web Paramètres de conférence conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="abb07-151">(Facultatif) Dans **les langues** secondaires (quatre au maximum), cliquez sur Ajouter, sélectionnez une ou plusieurs langues supplémentaires que vous souhaitez prendre en charge pour les appelants de ce numéro d’accès à la conférence, puis cliquez sur  **OK.**</span><span class="sxs-lookup"><span data-stu-id="abb07-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="abb07-152">Vous pouvez choisir jusqu’à quatre langues secondaires pour chaque numéro d’accès à la connexion.</span><span class="sxs-lookup"><span data-stu-id="abb07-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="abb07-153">Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de conférence lorsqu’ils participent à une conférence.</span><span class="sxs-lookup"><span data-stu-id="abb07-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="abb07-154">Pour ajouter une région pour le numéro d’accès à la connexion, sous Régions associées, cliquez sur **Ajouter,** cliquez sur une ou plusieurs régions associées aux plans de numérotation pour ce numéro d’accès, puis cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="abb07-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="abb07-155">Pour supprimer une région du numéro d’accès à la connexion, sous **Régions** associées, cliquez sur la région à supprimer, puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="abb07-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="abb07-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="abb07-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="abb07-157">Modifier les numéros d’accès à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="abb07-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="abb07-158">Pour modifier les numéros d’accès aux appels, utilisez l’cmdlet **Set-CsDialInConferencingAccessNumber.**</span><span class="sxs-lookup"><span data-stu-id="abb07-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="abb07-159">La commande suivante modifie la propriété DisplayName du numéro d’accès à la conférence téléphonique dont l’identité est sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="abb07-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="abb07-160">Dans cet exemple, le nom complet est « Redmond Dial-In Access Number » :</span><span class="sxs-lookup"><span data-stu-id="abb07-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="abb07-161">Dans l’exemple suivant, le numéro d’accès aux conférences téléphoniques avec l’identité sip:RedmondDialIn@litwareinc.com est modifié pour inclure deux régions : Redmond et Seattle.</span><span class="sxs-lookup"><span data-stu-id="abb07-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="abb07-162">Pour cela, le paramètre Region est appelé, suivi des deux régions (deux valeurs de chaînes séparées par une virgule).</span><span class="sxs-lookup"><span data-stu-id="abb07-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="abb07-163">Notez que cette commande échouera si les deux régions, Redmond et Seattle, ne sont pas déjà définies dans des plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="abb07-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="abb07-164">Pour plus d’informations, [voir Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abb07-164">For more information, see [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="abb07-165">Supprimer un numéro d’accès aux conférences téléphoniques</span><span class="sxs-lookup"><span data-stu-id="abb07-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="abb07-166">Vous pouvez supprimer un numéro d’accès aux conférences téléphoniques à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="abb07-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="abb07-167">Supprimer un numéro d’accès aux conférences téléphoniques à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="abb07-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="abb07-168">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abb07-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="abb07-169">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="abb07-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="abb07-170">Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Numéro d’accès à **la conférence.**</span><span class="sxs-lookup"><span data-stu-id="abb07-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="abb07-171">Dans la page, cliquez sur le numéro de connexion à supprimer dans la liste, cliquez sur **Modifier,** puis cliquez sur **Supprimer.**</span><span class="sxs-lookup"><span data-stu-id="abb07-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="abb07-172">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="abb07-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="abb07-173">Supprimer un numéro d’accès aux conférences téléphoniques à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="abb07-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="abb07-174">Pour supprimer un numéro d’accès aux conférences téléphoniques, utilisez **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="abb07-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="abb07-175">La commande suivante supprime le numéro d’accès aux conférences téléphoniques avec l’identité sip:RedmondDialInAccess@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="abb07-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="abb07-176">La commande suivante supprime tous les numéros d’accès aux conférences téléphoniques associés à la région Northwest :</span><span class="sxs-lookup"><span data-stu-id="abb07-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="abb07-177">La commande suivante supprime tous les numéros d’accès aux conférences téléphoniques dont l’italien est la langue principale :</span><span class="sxs-lookup"><span data-stu-id="abb07-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="abb07-178">Pour plus d’informations, [voir Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="abb07-178">For more information, see [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
