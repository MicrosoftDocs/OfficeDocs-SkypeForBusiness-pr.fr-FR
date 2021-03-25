---
title: Gérer le mappage de touches pour les commandes DTMF dans Skype Entreprise Server
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Résumé : Découvrez comment gérer le mappage de touches des commandes DTMF (dual-tone multi-frequency) dans Skype Entreprise Server.'
ms.openlocfilehash: 6b409ccce10128fdd7776e3ea77d6ee17d4a49f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119443"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="89fa5-103">Gérer le mappage de touches pour les commandes DTMF dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="89fa5-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="89fa5-104">**Résumé :** Découvrez comment gérer le mappage de touches des commandes DTMF (dual-tone multi-frequency) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="89fa5-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="89fa5-105">Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF).</span><span class="sxs-lookup"><span data-stu-id="89fa5-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="89fa5-106">Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur microphone ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone.</span><span class="sxs-lookup"><span data-stu-id="89fa5-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="89fa5-107">Pour gérer les clés utilisées pour les commandes DTMF, utilisez Skype Entreprise Server Management Shell avec les cmdlets **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration** et **New-CsDialinConferencingDtmfConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="89fa5-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="89fa5-108">Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="89fa5-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="89fa5-109">Gérer le mappage de touches des commandes DTMF</span><span class="sxs-lookup"><span data-stu-id="89fa5-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="89fa5-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="89fa5-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="89fa5-111">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="89fa5-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="89fa5-112">Pour afficher les paramètres DTMF utilisés pour les conférences téléphoniques, exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="89fa5-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="89fa5-113">Pour modifier les paramètres DTMF utilisés pour les conférences téléphoniques, exécutez l’cmdlet suivante et spécifiez la touche à utiliser pour chaque option à modifier :</span><span class="sxs-lookup"><span data-stu-id="89fa5-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="89fa5-114">(Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez la cmdlet **New-CsDialinConferencingDtmfConfiguration** avec une identité de site.</span><span class="sxs-lookup"><span data-stu-id="89fa5-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="89fa5-115">L’exemple suivant permute la touche qui est activée pour activer ou désactiver les annonces et la touche qui est activée pour activer et désactiver le son de tous les participants.</span><span class="sxs-lookup"><span data-stu-id="89fa5-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="89fa5-116">Étant donné qu’aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres DTMF globaux :</span><span class="sxs-lookup"><span data-stu-id="89fa5-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="89fa5-117">Pour plus d’informations, voir [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)et [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89fa5-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
