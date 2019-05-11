---
title: Afficher les informations de configuration de jonction dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.
ms.openlocfilehash: dab6a53d76bdc33ddd39117afd7f8b32a1c9c170
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926085"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de jonction dans Skype pour Business Server

Paramètres de configuration de jonction SIP définissent les relations et les fonctionnalités entre un serveur de médiation et la passerelle de réseau téléphonique commuté, un autocommutateur public-IP (PBX) ou un contrôleur de bordure de Session (SBC) au niveau du fournisseur de service.

- si la déviation du trafic multimédia doit être activée sur les jonctions ;
- Les conditions dans lesquelles les paquets Real-Time transport control protocol (RTCP) sont envoyés.
- Ou non sécurisé en temps réel (chiffrement SRTP protocol) est requis sur chaque jonction.

Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

**Pour afficher les informations de configuration de jonction SIP à l’aide de Skype pour Business Server Control Panel**

1. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales**, puis cliquez sur **Configuration de jonction**.
2. Sous l’onglet **Configuration de jonction** , vous verrez une liste de toutes vos collections de paramètres de la configuration de jonction ; pour chaque collection, vous verrez des valeurs pour les propriétés **nom**, **étendue**, **état**et **le contournement de média** , ainsi que le nombre **d’utilisations PSTN**, **règles de numéros de l’appel**et **appelées règles numéros** associé avec la collection. Pour obtenir des informations supplémentaires sur une collection de paramètres de configuration de jonction, cliquez sur la collection d’intérêt, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**. Notez que vous pouvez afficher des informations détaillées que pour une collection de paramètres de configuration de jonction à la fois.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration de jonction SIP à l’aide des applets de commande Windows PowerShell

SIP configuration de jonction paramètres peuvent être affichés à l’aide de Skype pour Business Server PowerShell et l’applet de commande Get-CsTrunkConfiguration. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session Windows PowerShell à distance. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, voir l’article de blog Lync Server Windows PowerShell « Rapide démarrer : gestion de Microsoft Lync Server 2010 à l’aide d’à distance PowerShell » à http://go.microsoft.com/fwlink/p/?linkId=255876. REMPLACER OU SUPPRIMER CE LIEN.


**Pour afficher les informations de configuration de jonction SIP**

Pour afficher des informations sur tous vos paramètres de configuration de jonction SIP, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :

`Get-CsTrunkConfiguration`

Vous obtiendrez des indications semblables à ceci :

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
Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .



