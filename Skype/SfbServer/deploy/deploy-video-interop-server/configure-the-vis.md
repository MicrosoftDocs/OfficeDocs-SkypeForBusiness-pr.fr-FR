---
title: Configuration du serveur d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : Configurer le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a>Configuration du serveur d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
 
**Résumé :** Configurez le rôle de serveur d’interopérabilité vidéo (VIS) dans Skype pour Business Server 2015.
  
 Configurer les paramètres de la VIS associer des troncs vidéo à l’aide de Windows PowerShell. Une configuration de jonction de vidéo avec une étendue globale est créée une fois que le service de rapport est installé. Cette configuration de jonction de vidéo est appliquée par la VIS à tous les puits qui n’ont pas de configuration trunk vidéo avec une portée plus spécifique. Notez que la configuration de jonction vidéo est une collection de paramètres qui est applicable aux puits vidéo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurer le tronçon vidéo et le plan de numérotation

Utilisation de commandes Windows PowerShell suivantes pour spécifier la configuration de jonction de vidéo et de la connexion à plan sera associé à le trunk(s) nouvellement défini, définies dans le Document de topologie entre les VIS et toutes les passerelles vidéo. Tous ces paramètres sont configurables aux niveaux global, du site ou du service (passerelle vidéo). 
  
Un plan d’appel avec une étendue globale est créé par Skype pour le déploiement du serveur de l’entreprise. Ce plan de numérotation est appliqué par rapport à tous les puits qui n’ont pas tous accès à planifier avec une portée plus spécifique. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurer le rapport à l’aide de Windows PowerShell

1. Créer une configuration de jonction vidéo (il s’agit d’un ensemble de paramètres) pour les utiliser sur le tronc de la VIS et CUCM, à l’aide de l’applet de commande Windows PowerShell suivante :
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    S’il existe un trunk vidéo existant qui doit être modifié, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Pour afficher les paramètres associés à une configuration de jonction de vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Pour supprimer une configuration de jonction de vidéo particulier, utilisez l’applet de commande Windows PowerShell suivante (Notez que la configuration de jonction de vidéo global sera appliquée s’il n’existe pas une configuration de jonction de vidéo plus précisément la portée pour un tronc particulier) :
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Établir un plan de numérotation à associer à la jonction, à l’aide des applets de commande Windows PowerShell suivante :
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

La commande **Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut afin qu’elle n’interfère pas avec l’interaction CUCM ou du VIS attendue.
> [!NOTE]
> [Supprimer-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) permet de supprimer un plan de numérotation.
  
Pour un appel SIP le tronc vidéo d’une passerelle vidéo dont la demande l’URI contient un nombre de non-E.164, VIS lira le nom du plan de numérotation associé du tronc associé et inclura le nom de plan d’accès à distance dans la partie de contexte téléphonique de l’URI de la demande dans l’invitation que VI S envoie à la partie frontale. L’Application de traduction sur le Front-End extrait et applique les règles de normalisation associés à l’URI de la demande, le plan de numérotation.
## <a name="trunk-configuration-options"></a>Options de configuration de tronçon

Les applets de commande Windows PowerShell pour la configuration vidéo trunk mentionnées précédemment sont nouveaux dans le Skype pour Business Server 2015. Les paramètres associés à la configuration de tronçon vidéo requièrent une brève explication.
  
 **GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si les paquets RTCP sont envoyées à partir de la VTC à l’égard d’appels actifs. Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction. Si le paramètre GatewaySendsRtcpForActiveCalls est défini sur True, le serveur d’interopérabilité vidéo (VIS) peut mettre fin à un appel s’il ne reçoit aucun paquet RTCP dans un délai de plus de 30 secondes. La valeur par défaut est **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si les paquets RTCP continueront d’être envoyées via le trunk pour les appels qui ont été placés en attente et si aucun paquet de média n’est attendus dans les deux sens. Le serveur d’interopérabilité vidéo (VIS) peut mettre fin à l’appel s’il ne reçoit aucun paquet RTCP du système de vidéoconférence (VTC) lorsque l’appel est en attente. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableMediaEncryptionForSipOverTls** Ce paramètre Active ou désactive les SRTP pour le média lorsque le protocole SIPTransport est défini sur TLS. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableSessionTimer** Ce paramètre Active ou désactive les compteurs de session sur le côté de VIS pour chaque boîte de dialogue SIP associé à la vidéo SIP trunk. La valeur par défaut est **False**.
  
 **ForwardErrorCorrectionType** Ce paramètre est utilisé pour déterminer si la Correction FEC (Forward Error) pour le flux vidéo est à appliquer sur la jambe entre le serveur d’interopérabilité vidéo et une passerelle vidéo. ForwardErrorCorrectionType de paramètre « None » désactive FEC entre VIS et vidéo passerelle/VTC. ForwardErrorCorrectionType à « Cisco » permet d’activer FEC compatible avec les passerelles de vidéo par Cisco, tels que Cisco Unified Communications Manager (CUCM). La valeur par défaut est **Aucun**.
  
## <a name="see-also"></a>Voir aussi

#### 

[Configurer CUCM pour l’interopérabilité avec Skype pour Business Server 2015](configure-cucm-for-interoperation.md)

