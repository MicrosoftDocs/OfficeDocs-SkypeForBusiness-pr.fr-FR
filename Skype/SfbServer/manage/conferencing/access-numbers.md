---
title: 'Gestion des numéros d’accès pour les conférences rendez-vous dans Skype entreprise Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Résumé : Découvrez comment gérer les numéros d’accès à une conférence rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: bd2aff1789c040667062d34b8bc037fd0543c029
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991919"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="9152f-103">Gestion des numéros d’accès pour les conférences rendez-vous dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9152f-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="9152f-104">**Résumé :** Découvrez comment gérer les numéros d’accès à une conférence rendez-vous dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9152f-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="9152f-105">Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences.</span><span class="sxs-lookup"><span data-stu-id="9152f-105">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="9152f-106">Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-106">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="9152f-107">Cette rubrique décrit comment afficher, modifier ou supprimer des numéros d’accès à des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="9152f-108">Pour plus d’informations sur la création d’un numéro d’accès à une conférence rendez-vous, voir [configurer des conférences rendez-vous dans Skype entreprise Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="9152f-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="9152f-109">Affichage des numéros d’accès aux conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="9152f-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="9152f-110">Vous pouvez afficher les numéros d’accès à une conférence rendez-vous à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9152f-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9152f-111">Afficher les numéros d’accès rendez-vous à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9152f-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9152f-112">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9152f-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9152f-113">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9152f-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9152f-114">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="9152f-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="9152f-115">Dans la page **Numéro d’accès entrant**, cliquez sur le numéro d’accès à afficher.</span><span class="sxs-lookup"><span data-stu-id="9152f-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="9152f-116">Dans **Modifier**, activez la case à cocher **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9152f-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9152f-117">Afficher les numéros d’accès rendez-vous à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9152f-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9152f-118">Pour afficher des informations sur des numéros d’accès à des conférences rendez-vous, utilisez l’applet de commande **Get-Cs DialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="9152f-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="9152f-119">La commande suivante renvoie une collection de tous les numéros d’accès à une conférence rendez-vous configurés pour une utilisation au sein de l’Organisation :</span><span class="sxs-lookup"><span data-stu-id="9152f-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="9152f-120">Voici un exemple du type d’informations renvoyées :</span><span class="sxs-lookup"><span data-stu-id="9152f-120">The following is an example of the type of information returned:</span></span>
  
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

<span data-ttu-id="9152f-121">Pour plus d’informations, consultez la rubrique [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9152f-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="9152f-122">Modification des numéros d’accès à des conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="9152f-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="9152f-123">Vous pouvez modifier les numéros d’accès rendez-vous à l’aide du panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9152f-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9152f-124">Modification des numéros d’accès rendez-vous à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9152f-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="9152f-125">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9152f-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9152f-126">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9152f-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9152f-127">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="9152f-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="9152f-128">Dans la page **Numéro d’accès entrant**, cliquez sur l’un des numéros d’accès entrant dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9152f-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9152f-p103">Utiliser le champ de recherche pour rechercher le contenu d’une colonne dans la liste des numéros d’accès entrant peut ne pas produire les résultats que vous attendez. Par conséquent, triez la liste selon la colonne qui vous intéresse pour identifier le numéro d’accès entrant que vous voulez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="9152f-p103">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="9152f-131">Dans **Numéro affiché**, tapez le numéro de téléphone que les utilisateurs du réseau téléphonique commuté (RTC) composent pour rejoindre une conférence.</span><span class="sxs-lookup"><span data-stu-id="9152f-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="9152f-132">Ce numéro est affiché dans les invitations aux réunions et dans la page web des paramètres des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="9152f-133">In **Nom d’affichage**, tapez la description du numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="9152f-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="9152f-134">Il s’agit du nom associé au numéro d’accès à la Conférence rendez-vous dans les résultats de recherche de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="9152f-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="9152f-135">Ce nom est affiché dans le client lorsqu’un utilisateur appelle le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="9152f-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="9152f-p105">Dans **URI de ligne**, tapez le numéro E.164 du numéro d’accès entrant au format d’URI TEL, avec le symbole + avant le numéro et sans espace. Par exemple, tel :+14255550200.</span><span class="sxs-lookup"><span data-stu-id="9152f-p105">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9152f-138">Le même URI de ligne ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="9152f-139">Dans **URI SIP**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9152f-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="9152f-140">Dans la zone de texte, tapez un URI SIP (Session Initiation Protocol) unique pour ce numéro d’accès à une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="9152f-141">Cet URI SIP est affiché à différents emplacements, y compris, mais sans s’y limiter, les messages de notification d’appel et les versions précédentes des clients Lync.</span><span class="sxs-lookup"><span data-stu-id="9152f-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9152f-p107">Le même URI SIP ne peut pas être réutilisé par un autre numéro d’accès à une conférence rendez-vous. Il n’est pas possible de modifier l’URI SIP une fois que le numéro d’accès est créé. Le seul moyen de modifier l’URI SIP est de supprimer et de recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="9152f-p107">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="9152f-145">Dans la zone de liste déroulante, cliquez sur le domaine de l’application de surveillance des conférences qui prend en charge ce numéro d’accès rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="9152f-146">Dans **Pool**, cliquez sur le pool qui exécute l’instance d’Intendant Conférence qui prend en charge ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="9152f-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9152f-147">Si vous devez modifier le pool après avoir créé le numéro d’accès, vous devez utiliser l’applet de commande **Move-CsApplicationEndpoint** ou supprimer et recréer le numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="9152f-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="9152f-148">Dans **Langue principale**, cliquez sur la langue des invites pour ce numéro d’accès entrant.</span><span class="sxs-lookup"><span data-stu-id="9152f-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="9152f-p108">La langue principale est la langue que l’Intendant Conférence utilise pour répondre aux appels. Les langues prises en charge sont affichées avec chaque numéro de téléphone d’accès dans la page web des paramètres des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9152f-p108">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="9152f-151">(Facultatif) Dans **Langues secondaires (quatre au maximum)**, cliquez sur **Ajouter**, sélectionnez les langues supplémentaires que vous souhaitez prendre en charge pour les personnes qui appellent ce numéro d’accès entrant, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9152f-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="9152f-p109">Vous pouvez sélectionner jusqu’à quatre langues secondaires pour chaque numéro d’accès entrant. Les utilisateurs peuvent sélectionner une langue secondaire avant d’entrer l’ID de la conférence à laquelle ils souhaitent participer.</span><span class="sxs-lookup"><span data-stu-id="9152f-p109">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="9152f-154">Pour ajouter une région pour le numéro d’accès à la Conférence rendez-vous, sous **régions associées**, cliquez sur **Ajouter**, sélectionnez une ou plusieurs régions associées au plan de numérotation pour ce numéro d’accès rendez-vous, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9152f-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="9152f-155">Pour supprimer une région du numéro d’accès entrant, sous **Régions associées**, cliquez sur la région que vous souhaitez supprimer, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9152f-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="9152f-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9152f-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9152f-157">Modification des numéros d’accès rendez-vous à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9152f-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9152f-158">Pour modifier des numéros d’accès aux conférences rendez-vous, utilisez l’applet de commande **Set-Cs DialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="9152f-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="9152f-p110">La commande ci-dessous modifie la propriété DisplayName pour le numéro d’accès de conférence rendez-vous avec la propriété Identity sip:RedmondDialIn@litwareinc.com. Dans cet exemple, le nom complet est défini sur « Redmond Dial-In Access Number » :</span><span class="sxs-lookup"><span data-stu-id="9152f-p110">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com. In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="9152f-p111">Dans l’exemple ci-dessous, le numéro d’accès de conférence rendez-vous avec la propriété Identity sip:RedmondDialIn@litwareinc.com est modifié pour inclure deux régions : Redmond et Seattle. Pour cela, le paramètre Region est appelé, suivi des deux régions (deux valeurs de chaînes séparées par une virgule). Notez que cette commande échouera si les deux régions, Redmond et Seattle, ne sont pas déjà définies dans des plans de numérotation.</span><span class="sxs-lookup"><span data-stu-id="9152f-p111">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle. To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas). Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="9152f-164">Pour plus d’informations, consultez la rubrique [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9152f-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="9152f-165">Suppression d’un numéro d’accès de conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="9152f-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="9152f-166">Vous pouvez supprimer un numéro d’accès à une conférence rendez-vous en utilisant le panneau de configuration Skype entreprise Server ou en utilisant Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9152f-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9152f-167">Supprimer un numéro d’accès à une conférence rendez-vous à l’aide du panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9152f-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9152f-168">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="9152f-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="9152f-169">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9152f-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9152f-170">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Numéro d’accès entrant**.</span><span class="sxs-lookup"><span data-stu-id="9152f-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="9152f-171">Dans la page, cliquez sur le numéro d’accès que vous souhaitez supprimer dans la liste, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9152f-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9152f-172">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9152f-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9152f-173">Supprimer un numéro d’accès à une conférence rendez-vous à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9152f-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="9152f-174">Pour supprimer un numéro d’accès de conférence rendez-vous, utilisez l’applet de commande **Remove-CsDialInConferencingAccessNumber**.</span><span class="sxs-lookup"><span data-stu-id="9152f-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="9152f-175">La commande ci-dessous permet de supprimer le numéro d’accès de conférence rendez-vous doté de l’ID sip:RedmondDialInAccess@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="9152f-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="9152f-176">La commande ci-dessous permet de supprimer tous les numéros d’accès de conférence rendez-vous associés à la région Northwest :</span><span class="sxs-lookup"><span data-stu-id="9152f-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="9152f-177">La commande ci-dessous permet de supprimer tous les numéros d’accès de conférence rendez-vous où l’italien est la langue principale :</span><span class="sxs-lookup"><span data-stu-id="9152f-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="9152f-178">Pour plus d’informations, consultez la rubrique [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9152f-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

