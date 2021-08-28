---
title: Afficher les informations de configuration de la Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services.
ms.openlocfilehash: 204f6f17387499719cf3b4bbe33638a849a4e363
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614064"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de la Skype Entreprise Server

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services.

- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

**Pour afficher les informations de configuration d’une Skype Entreprise Server SIP à l’aide du Panneau de configuration**

1. Dans le Skype Entreprise Server de configuration, cliquez sur **Routage** des voix, puis sur **Configuration de la trunk .**
2. Sous **l’onglet Configuration** de la trunk, vous verrez une liste de toutes vos collections de paramètres de configuration de la trunk; Pour chaque collection, vous verrez des valeurs  pour les propriétés **Nom,** Étendue,  **État** et Contournement  de média, ainsi que le nombre d’utilisations **PSTN,** les règles de numéro d’appel et les règles de numéro appelé associées à la collection. Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de la trunk, cliquez sur la collection d’intérêts, cliquez sur **Modifier,** puis cliquez sur **Afficher les détails.** Notez que vous ne pouvez afficher des informations détaillées que pour une collection de paramètres de configuration de trunk à la fois.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration d’une Windows PowerShell SIP

Vous pouvez afficher les paramètres de configuration de la Skype Entreprise Server SIP à l’aide de PowerShell et Get-CsTrunkConfiguration cmdlet. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog Lync Server Windows PowerShell « Démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell » à l’emplacement https://go.microsoft.com/fwlink/p/?linkId=255876 suivant. REMPLACEZ OU SUPPRIMEZ CE LIEN.


**Pour afficher les informations de configuration d’une trunk SIP**

Pour afficher des informations sur tous vos paramètres de configuration de la trunk SIP, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :

```powershell
Get-CsTrunkConfiguration
```

Cette action a pour effet de renvoyer des informations similaires à ce qui suit :

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
Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Get-CsTrunkConfiguration.](/powershell/module/skype/Get-CsTrunkConfiguration)