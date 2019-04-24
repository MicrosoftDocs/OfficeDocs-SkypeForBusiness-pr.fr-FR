---
title: Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : Configurez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.'
ms.openlocfilehash: 1cdc03fea116b5c41eaca13b4349ffc340dbc061
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219606"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurer le serveur d’interopérabilité vidéo dans Skype pour Business Server
 
**Résumé :** Configurez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server.
  
 Configurer les paramètres du rapport associer des jonctions vidéo à l’aide de Windows PowerShell. Une configuration de jonction vidéo avec une étendue globale est créée une fois que le service de rapport est installé. Cette configuration de jonction vidéo est appliquée à l’égard à toutes les jonctions qui n’ont pas de configuration de jonction vidéo avec une étendue plus spécifique. Notez que la configuration de tronçon vidéo est une collection de paramètres qui s’applique à jonctions vidéo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurer le tronçon vidéo et le plan de numérotation

Utiliser les commandes Windows PowerShell suivantes pour spécifier la configuration de jonction vidéo et la numérotation plan sera associé à la trunk(s) nouvellement défini définis dans le Document de topologie entre les VIS et toutes les passerelles vidéo. Tous ces paramètres sont configurables aux niveaux global, du site ou du service (passerelle vidéo). 
  
Un plan de numérotation avec une étendue globale est créé par Skype pour le déploiement de serveur d’entreprise. Ce plan de numérotation est appliqué par rapport à toutes les jonctions qui ne disposent pas d’un accès à planifier avec une étendue plus spécifique. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurer le rapport à l’aide de Windows PowerShell

1. Créer une nouvelle configuration de jonction vidéo (une collection de paramètres) afin d’utiliser sur la jonction entre la VIS et Cisco Unified Communications Manager (CallManager ou CUCM), à l’aide de l’applet de commande Windows PowerShell suivante :
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    S’il existe une jonction existante vidéo qui doit être modifié, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Pour afficher les paramètres associés à une configuration de tronçon vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Pour supprimer une configuration de tronçon vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante (Notez que la configuration de tronçon vidéo global sera appliquée si n’est pas une configuration de jonction vidéo plus précisément étendue définie pour un tronçon particulier) :
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Établissez un plan de numérotation à associer à la jonction, à l’aide des applets de commande Windows PowerShell suivantes :
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

La commande **Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut afin qu’elle n’interfère pas avec l’interaction CUCM ou du VIS attendue.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisée pour supprimer un plan de numérotation.
  
Pour un appel vidéo de jonction SIP à partir d’une passerelle vidéo dont URI de demande contient un numéro non E.164, VIS ne lit pas le nom du plan de numérotation associé à la jonction associé et inclut le nom de plan de numérotation dans le composant de contexte téléphonique de l’URI demandé dans l’invitation que VI S envoie vers le serveur frontal. L’Application de traduction sur le serveur frontal extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de demande.
## <a name="trunk-configuration-options"></a>Options de configuration de tronçon

Les applets de commande Windows PowerShell pour la configuration de jonction vidéo indiqué précédemment ont été Nouveautés Skype pour Business Server 2015. Les paramètres associés à la configuration de tronçon vidéo requièrent une brève explication.
  
 **GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si des paquets RTCP sont envoyés à partir de la VTC à l’égard pour les appels actifs. Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction. Si le paramètre GatewaySendsRtcpForActiveCalls est défini sur True, le serveur d’interopérabilité vidéo (VIS) peut mettre fin à un appel s’il ne reçoit aucun paquet RTCP dans un délai de plus de 30 secondes. La valeur par défaut est **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si des paquets RTCP continuent d’être envoyés sur le tronçon pour les appels qui ont été mis en attente et aucune paquets de médias ne sont attendus dans les deux directions. Le serveur d’interopérabilité vidéo (VIS) peut mettre fin à l’appel s’il ne reçoit aucun paquet RTCP du système de vidéoconférence (VTC) lorsque l’appel est en attente. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableMediaEncryptionForSipOverTls** Ce paramètre Active ou désactive le chiffrement SRTP pour le média lorsque le protocole SIPTransport est défini sur TLS. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableSessionTimer** Ce paramètre Active ou désactive les temporisateurs de session sur le côté de VIS pour chaque boîte de dialogue SIP associé à la jonction SIP vidéo. La valeur par défaut est **False**.
  
 **ForwardErrorCorrectionType** Ce paramètre est utilisé pour déterminer si FEC Forward Error Correction () pour le flux vidéo doit être appliquée sur le segment entre le serveur d’interopérabilité vidéo et une passerelle vidéo. Paramètre ForwardErrorCorrectionType sur « None » désactive FEC entre VIS et vidéo passerelle/VTC. ForwardErrorCorrectionType à « Cisco » permet d’activer FEC compatible avec les passerelles vidéo par Cisco, tels que Cisco Unified Communications Manager (CUCM). La valeur par défaut est **Aucun**.
  
## <a name="see-also"></a>Voir aussi

[Configurer CUCM pour l’interopérabilité avec Skype pour Business Server](configure-cucm-for-interoperation.md)
