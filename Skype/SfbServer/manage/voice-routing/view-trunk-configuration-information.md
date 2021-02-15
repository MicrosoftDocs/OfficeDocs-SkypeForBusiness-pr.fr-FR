---
title: Afficher les informations de configuration de la trunk dans Skype Entreprise Server
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
description: Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826164"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="dc246-103">Afficher les informations de configuration de la trunk dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dc246-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="dc246-104">Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="dc246-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="dc246-105">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="dc246-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="dc246-106">Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="dc246-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="dc246-107">L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="dc246-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="dc246-108">Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="dc246-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="dc246-109">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="dc246-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="dc246-110">**Pour afficher les informations de configuration d’une trunk SIP à l’aide du Panneau de configuration de Skype Entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="dc246-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="dc246-111">Dans le Panneau de configuration de Skype Entreprise Server, cliquez sur **Routage** des voix, puis cliquez sur **Configuration de la configuration des branches.**</span><span class="sxs-lookup"><span data-stu-id="dc246-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="dc246-112">Sous **l’onglet Configuration** de la trunk, vous verrez une liste de toutes vos collections de paramètres de configuration de la trunk; Pour chaque collection, vous verrez des valeurs  pour les propriétés **Nom,** Étendue,  **État** et Contournement  de média, ainsi que le nombre d’utilisations **PSTN,** les règles de numéro d’appel et les règles de numéro appelé associées à la collection.</span><span class="sxs-lookup"><span data-stu-id="dc246-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="dc246-113">Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de la trunk, cliquez sur la collection d’intérêts, cliquez sur **Modifier,** puis cliquez sur **Afficher les détails.**</span><span class="sxs-lookup"><span data-stu-id="dc246-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="dc246-114">Notez que vous ne pouvez afficher des informations détaillées que pour une collection de paramètres de configuration de trunk à la fois.</span><span class="sxs-lookup"><span data-stu-id="dc246-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc246-115">Affichage des informations de configuration d’une Windows PowerShell SIP</span><span class="sxs-lookup"><span data-stu-id="dc246-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dc246-116">Vous pouvez afficher les paramètres de configuration de la Get-CsTrunkConfiguration SIP à l’aide de Skype Entreprise Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc246-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="dc246-117">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc246-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="dc246-118">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article du blog Lync Server Windows PowerShell « Démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell » à https://go.microsoft.com/fwlink/p/?linkId=255876 l’adresse .</span><span class="sxs-lookup"><span data-stu-id="dc246-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="dc246-119">REMPLACEZ OU SUPPRIMEZ CE LIEN.</span><span class="sxs-lookup"><span data-stu-id="dc246-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="dc246-120">**Pour afficher les informations de configuration d’une trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="dc246-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="dc246-121">Pour afficher des informations sur tous les paramètres de configuration de votre trunk SIP, tapez la commande suivante dans l’environnement de ligne de commande Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="dc246-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="dc246-122">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="dc246-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="dc246-123">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="dc246-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



