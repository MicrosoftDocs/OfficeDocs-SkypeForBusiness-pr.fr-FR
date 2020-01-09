---
title: Afficher les informations de configuration de Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.
ms.openlocfilehash: 8fb180994fdcd8409b0776a2fcaee6316110a36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992551"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="7aff3-103">Afficher les informations de configuration de Trunk dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="7aff3-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="7aff3-104">Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="7aff3-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="7aff3-105">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="7aff3-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="7aff3-106">Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.</span><span class="sxs-lookup"><span data-stu-id="7aff3-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="7aff3-107">Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.</span><span class="sxs-lookup"><span data-stu-id="7aff3-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="7aff3-108">Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="7aff3-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="7aff3-109">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="7aff3-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="7aff3-110">**Pour afficher les informations de configuration du Trunk SIP en utilisant le panneau de configuration Skype entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="7aff3-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="7aff3-111">Dans le panneau de configuration Skype entreprise Server, cliquez sur **routage des communications vocales**, puis cliquez sur **configuration de Trunk**.</span><span class="sxs-lookup"><span data-stu-id="7aff3-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="7aff3-112">Dans l’onglet **configuration de Trunk** , vous verrez la liste de toutes vos collections de paramètres de configuration de Trunk ; pour chaque collection, des valeurs s’appliquent aux propriétés **Name**, **scope**, **State**et de **contournement de média** , ainsi que le nombre d' **utilisations PSTN**, de **règles de numéro d’appel**et de **règles de numérotation** associées à la collection.</span><span class="sxs-lookup"><span data-stu-id="7aff3-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="7aff3-113">Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de ligne, cliquez sur l’ensemble d’intérêt, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="7aff3-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="7aff3-114">Notez que vous pouvez afficher des informations détaillées pour une collection unique de paramètres de configuration de Trunk à la fois.</span><span class="sxs-lookup"><span data-stu-id="7aff3-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7aff3-115">Affichage des informations de configuration de Trunk SIP à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7aff3-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7aff3-116">Les paramètres de configuration de Trunk SIP peuvent être affichés à l’aide de Skype entreprise Server PowerShell et de l’applet de ligne Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7aff3-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="7aff3-117">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7aff3-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="7aff3-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype entreprise Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync http://go.microsoft.com/fwlink/p/?linkId=255876Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="7aff3-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="7aff3-119">REMPLACEZ OU SUPPRIMEZ CE LIEN.</span><span class="sxs-lookup"><span data-stu-id="7aff3-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="7aff3-120">**Pour afficher les informations de configuration du Trunk SIP**</span><span class="sxs-lookup"><span data-stu-id="7aff3-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="7aff3-121">Pour afficher des informations sur l’ensemble des paramètres de configuration de Trunk SIP, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="7aff3-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="7aff3-122">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="7aff3-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="7aff3-123">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="7aff3-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



