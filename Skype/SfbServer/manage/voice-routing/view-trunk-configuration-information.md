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
ms.openlocfilehash: 03b2ea63df8135edfdb3d63d9010aaace9266fd1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102990"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>Afficher les informations de configuration de la trunk dans Skype Entreprise Server

Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services.

- L’activation ou non du contournement de média sur les jonctions.
- Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).
- L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.

Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous. En outre, les administrateurs peuvent créer des collections personnalisées sur l’étendue du site ou l’étendue du service (pour le service de passerelle PSTN, uniquement).

**Pour afficher les informations de configuration d’une trunk SIP à l’aide du Panneau de configuration de Skype Entreprise Server**

1. Dans le Panneau de configuration de Skype Entreprise Server, cliquez sur **Routage** des voix, puis sur **Configuration de la configuration de la configuration des branches.**
2. Sous **l’onglet Configuration** de la trunk, vous verrez une liste de toutes vos collections de paramètres de configuration de la trunk; Pour chaque collection, vous verrez des valeurs  pour les propriétés **Nom,** Étendue,  **État** et Contournement  de média, ainsi que le nombre d’utilisations **PSTN,** les règles de numéro d’appel et les règles de numéro appelé associées à la collection. Pour afficher des détails supplémentaires sur une collection de paramètres de configuration de la trunk, cliquez sur la collection d’intérêts, cliquez sur **Modifier,** puis cliquez sur **Afficher les détails.** Notez que vous ne pouvez afficher des informations détaillées que pour une collection de paramètres de configuration de trunk à la fois.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de configuration d’une Windows PowerShell SIP

Vous pouvez afficher les paramètres de configuration de la Get-CsTrunkConfiguration SIP à l’aide de Skype Entreprise Server PowerShell. Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante Windows PowerShell. Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog Lync Server Windows PowerShell « Démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell » à https://go.microsoft.com/fwlink/p/?linkId=255876 l’adresse . REMPLACEZ OU SUPPRIMEZ CE LIEN.


**Pour afficher les informations de configuration d’une trunk SIP**

Pour afficher des informations sur tous les paramètres de configuration de votre trunk SIP, tapez la commande suivante dans l’environnement de ligne de commande Skype Entreprise Server Management Shell, puis appuyez sur Entrée :

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