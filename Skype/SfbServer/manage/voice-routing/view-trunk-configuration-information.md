---
title: Afficher les informations de configuration de Trunk dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.
ms.openlocfilehash: 40820729727ec02e5494e69c773d7fbd3d7b1154
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888483"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de Trunk dans Skype entreprise Server

Les paramètres de configuration du Trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté (PSTN), un échange de succursale public (PBX) ou un contrôleur de bordure de session (SBC) au fournisseur de services.

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets de contrôle de transport en temps réel (RTCP) sont envoyés.
- Le chiffrement SRTP (Secure Real-Time Protocol) est requis sur chaque Trunk.

Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

**Pour afficher les informations de configuration du Trunk SIP en utilisant le panneau de configuration Skype entreprise Server**

1. Dans le panneau de configuration Skype entreprise Server, cliquez sur **routage des communications vocales**, puis cliquez sur **configuration de Trunk**.
2. Dans l’onglet **configuration de Trunk** , vous verrez la liste de toutes vos collections de paramètres de configuration de Trunk ; pour chaque collection, des valeurs s’appliquent aux propriétés **Name**, **scope**, **State**et de **contournement de média** , ainsi que le nombre d' **utilisations PSTN**, de **règles de numéro d’appel**et de **règles de numérotation** associées à la collection. Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de ligne, cliquez sur l’ensemble d’intérêt, cliquez sur **modifier**, puis sur **afficher les détails**. Notez que vous pouvez afficher des informations détaillées pour une collection unique de paramètres de configuration de Trunk à la fois.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de Trunk SIP à l’aide des cmdlets Windows PowerShell

Les paramètres de configuration de Trunk SIP peuvent être affichés à l’aide de Skype entreprise Server PowerShell et de l’applet de ligne Get-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype entreprise Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync https://go.microsoft.com/fwlink/p/?linkId=255876Server 2010 à l’aide de Remote PowerShell ». REMPLACEZ OU SUPPRIMEZ CE LIEN.


**Pour afficher les informations de configuration du Trunk SIP**

Pour afficher des informations sur l’ensemble des paramètres de configuration de Trunk SIP, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :

```powershell
Get-CsTrunkConfiguration
```

Vous obtiendrez des indications semblables à ceci :

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
Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) .



