---
title: Configurer le serveur d’interconnexion vidéo dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : Configurez le rôle VIS (Video Interop Server) dans Skype Entreprise Server.'
ms.openlocfilehash: 4148cf404fba4718f56c3c8db7ffe180881b3ae7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835812"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurer le serveur d’interconnexion vidéo dans Skype Entreprise Server
 
**Résumé :** Configurez le rôle vis (Video Interop Server) dans Skype Entreprise Server.
  
 Configurez les paramètres que le VIS associera aux trunks vidéo à l’aide de Windows PowerShell. Une configuration de trunk vidéo avec une étendue globale est créée une fois le service VIS installé. Cette configuration de trunk vidéo est appliquée par le VIS à toutes les trunks qui n’ont pas de configuration de trunk vidéo avec une portée plus spécifique. Notez que la configuration de la vidéoconférente est une collection de paramètres applicables aux trunks vidéo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurer le plan de numérotation et le système de numérotation de la vidéo

Utilisez les commandes Windows PowerShell suivantes pour spécifier la configuration de la vidéo et le plan de numérotation à associer aux nouvelles connexions définies dans le document de topologie entre le VIS et toutes les passerelles vidéo. Tous ces paramètres peuvent être définies aux niveaux global, site ou service (passerelle vidéo). 
  
Un plan de numérotation avec une étendue globale est créé par déploiement Skype Entreprise Server déploiement. Ce plan de numérotation est appliqué par le VIS à toutes les connexions qui n’ont pas de plan de numérotation avec une étendue plus spécifique. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurer le VIS à l’aide Windows PowerShell

1. Créez une configuration de trunk vidéo (collection de paramètres) à utiliser sur la ligne entre le VIS et Cisco Unified Communications Manager (CallManager, ou CUCM), à l’aide de l’Windows PowerShell suivante :
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Si une trunk vidéo existante doit être modifiée, utilisez l’Windows PowerShell suivante :
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Pour afficher les paramètres associés à une configuration de trunk vidéo particulière, utilisez l’Windows PowerShell suivante :
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Pour supprimer une configuration de vidéoconférente particulière, utilisez l’cmdlet Windows PowerShell suivante (notez que la configuration de la trunk vidéo de portée globale sera appliquée s’il n’existe pas de configuration de trunk vidéo d’étendue plus spécifique pour une troncation particulière) :
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Établissez un plan de numérotation à associer à la trunk, à l’aide des cmdlets Windows PowerShell suivantes :
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

La **commande Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut qui interfère avec l’interaction VIS et CUCM attendue.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisé pour supprimer un plan de numérotation.
  
Pour un appel de connexion SIP vidéo à partir d’une passerelle vidéo dont l’URI de demande contient un numéro non E.164, le VIS lit le nom du plan de numérotation associé à la connexion associée et inclut le nom du plan de numérotation dans la partie contexte téléphonique de l’URI de demande dans l’invitation que le VIS envoie au frontal. L’application de traduction sur le frontal extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de demande.
## <a name="trunk-configuration-options"></a>Options de configuration de la trunk

Les Windows PowerShell cmdlets pour la configuration de la vidéoconférente mentionnées précédemment étaient nouvelles Skype Entreprise Server 2015. Les paramètres associés à la configuration de la vidéoconférente nécessitent une brève explication.
  
 **GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si des paquets RTCP sont envoyés du VTC au VIS pour les appels actifs. Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction. Si GatewaySendsRtcpForActiveCalls est définie sur True, le VIS peut mettre fin à un appel s’il ne reçoit pas de paquets RTCP pendant une période supérieure à 30 secondes. La valeur par défaut est **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si les paquets RTCP continuent d’être envoyés sur le secteur pour les appels qui ont été mis en attente et si aucun paquet multimédia n’est censé circuler dans les deux sens. Le VIS peut mettre fin à l’appel s’il n’y a aucun paquet RTCP qui circule du VTC au VIS pendant l’attente de l’appel. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est définie sur TCP, ce paramètre est ignoré.
  
 **EnableMediaEncryptionForSipOverTls** Ce paramètre active ou désactive SRTP pour les médias lorsque le protocole SIPTransport est paramétrant sur TLS. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est définie sur TCP, ce paramètre est ignoré.
  
 **EnableSessionTimer** Ce paramètre active ou désactive les timers de session côté VIS pour chaque boîte de dialogue SIP associée à la session SIP vidéo. La valeur par défaut est **False**.
  
 **ForwardErrorCorrectionType** Ce paramètre permet de déterminer si la correction des erreurs de retour (FEC) pour les flux vidéo doit être appliquée sur la partie entre le serveur d’opation vidéo et une passerelle vidéo. La définition de ForwardErrorCorrectionType sur « None » dés éteint le FEC entre le VIS et la passerelle vidéo/VTC. La définition de ForwardErrorCorrectionType sur « Cisco » active la compatibilité FEC avec les passerelles vidéo de Cisco, telles que Cisco Unified Communications Manager (CUCM). La valeur par défaut **est Aucun**.
  
## <a name="see-also"></a>Voir aussi

[Configurer CUCM pour l’interopération avec Skype Entreprise Server](configure-cucm-for-interoperation.md)