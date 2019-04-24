---
title: Afficher les informations de configuration de jonction dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.
ms.openlocfilehash: 6ba97fa4650b8d62be625256ff4d3b9a3bb7cc68
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195492"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="12f2b-103">Afficher les informations de configuration de jonction dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="12f2b-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="12f2b-104">Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.</span><span class="sxs-lookup"><span data-stu-id="12f2b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="12f2b-105">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="12f2b-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="12f2b-106">Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.</span><span class="sxs-lookup"><span data-stu-id="12f2b-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="12f2b-107">Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="12f2b-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="12f2b-108">Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="12f2b-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="12f2b-109">En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).</span><span class="sxs-lookup"><span data-stu-id="12f2b-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="12f2b-110">**Pour afficher les informations de configuration de jonction SIP à l’aide de Skype pour Business Server Control Panel**</span><span class="sxs-lookup"><span data-stu-id="12f2b-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="12f2b-111">Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.</span><span class="sxs-lookup"><span data-stu-id="12f2b-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="12f2b-112">Sous l’onglet **Configuration de jonction** , vous verrez une liste de toutes vos collections de paramètres de la configuration de jonction ; pour chaque collection, vous verrez des valeurs pour les propriétés **nom**, **étendue**, **état**et **le contournement de média** , ainsi que le nombre **d’utilisations PSTN**, **règles de numéros de l’appel**et **appelées règles numéros** associé avec la collection.</span><span class="sxs-lookup"><span data-stu-id="12f2b-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="12f2b-113">Pour obtenir des informations supplémentaires sur une collection de paramètres de configuration de jonction, cliquez sur la collection d’intérêt, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="12f2b-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="12f2b-114">Notez que vous pouvez afficher des informations détaillées que pour une collection de paramètres de configuration de jonction à la fois.</span><span class="sxs-lookup"><span data-stu-id="12f2b-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="12f2b-115">Affichage des informations de configuration de jonction SIP à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12f2b-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="12f2b-116">SIP configuration de jonction paramètres peuvent être affichés à l’aide de Skype pour Business Server PowerShell et l’applet de commande Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="12f2b-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="12f2b-117">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="12f2b-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="12f2b-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, voir l’article de blog Lync Server Windows PowerShell « Rapide démarrer : gestion de Microsoft Lync Server 2010 à l’aide d’à distance PowerShell » à http://go.microsoft.com/fwlink/p/?linkId=255876.</span><span class="sxs-lookup"><span data-stu-id="12f2b-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="12f2b-119">REMPLACER OU SUPPRIMER CE LIEN.</span><span class="sxs-lookup"><span data-stu-id="12f2b-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="12f2b-120">**Pour afficher les informations de configuration de jonction SIP**</span><span class="sxs-lookup"><span data-stu-id="12f2b-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="12f2b-121">Pour afficher des informations sur tous vos paramètres de configuration de jonction SIP, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="12f2b-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="12f2b-122">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="12f2b-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="12f2b-123">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="12f2b-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



