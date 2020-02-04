---
title: 'Lync Server 2013 : (Facultatif) Modification du mappage des clés des commandes DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="44ea1-102">(Facultatif) Modification du mappage des clés des commandes DTMF dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44ea1-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44ea1-103">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="44ea1-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="44ea1-104">Les utilisateurs de conférences rendez-vous peuvent appuyer sur les touches du clavier téléphonique pour exécuter des commandes de numérotation en fréquences vocales (DTMF).</span><span class="sxs-lookup"><span data-stu-id="44ea1-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="44ea1-105">Les commandes DTMF permettent aux utilisateurs qui prennent part à une conférence de contrôler les paramètres de conférence (tels que l’activation et la désactivation de leur micro ou le verrouillage et le déverrouillage de la conférence) à l’aide du clavier de leur téléphone.</span><span class="sxs-lookup"><span data-stu-id="44ea1-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="44ea1-106">Vous pouvez utiliser les applets de commande pour modifier les touches utilisées pour les commandes DTMF.</span><span class="sxs-lookup"><span data-stu-id="44ea1-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="44ea1-107">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="44ea1-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44ea1-108">Pour plus d’informations sur ces applets de commande et les options DTMF possibles, voir documentation de Lync Server Management Shell ou aide de la ligne de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="44ea1-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="44ea1-109">Pour modifier le mappage de clés des commandes DTMF</span><span class="sxs-lookup"><span data-stu-id="44ea1-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="44ea1-110">Connectez-vous à l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou en tant que membre du rôle **CS-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="44ea1-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="44ea1-111">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="44ea1-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="44ea1-112">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="44ea1-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="44ea1-113">Cette applet de connexion renvoie les paramètres DTMF utilisés pour la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="44ea1-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="44ea1-114">Exécutez l’applet de commande suivante et spécifiez la clé à utiliser pour chaque option que vous voulez modifier :</span><span class="sxs-lookup"><span data-stu-id="44ea1-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="44ea1-115">Cette applet de connexion modifie les paramètres DTMF utilisés pour la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="44ea1-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="44ea1-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="44ea1-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="44ea1-117">Cet exemple permute la touche enfoncée pour activer ou désactiver les annonces et la touche activée pour activer ou désactiver le micro de tous les participants.</span><span class="sxs-lookup"><span data-stu-id="44ea1-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="44ea1-118">Comme aucune identité n’est spécifiée, ces modifications s’appliquent aux paramètres du DTMF global.</span><span class="sxs-lookup"><span data-stu-id="44ea1-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="44ea1-119">(Facultatif) Si vous voulez créer des jeux de commandes DTMF supplémentaires pour des sites spécifiques, utilisez l’applet de commande **New-CsDialinConferencingDtmfConfiguration** avec une identité de site.</span><span class="sxs-lookup"><span data-stu-id="44ea1-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="44ea1-120">Lorsque vous créez des paramètres DTMF pour des sites, les paramètres de site sont prioritaires sur les paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="44ea1-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="44ea1-121">Pour plus d’informations, consultez la documentation de Lync Server Management Shell ou l’aide de la ligne de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="44ea1-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

