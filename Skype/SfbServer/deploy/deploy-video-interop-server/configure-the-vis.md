---
title: Configurer le serveur Video Interop dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Résumé : configurez le rôle serveur d’interopérabilité vidéo (a) dans Skype entreprise Server.'
ms.openlocfilehash: fb9dc36bcf2f1a6f1346705f74dd3cf2844a973c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003054"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurer le serveur Video Interop dans Skype entreprise Server
 
**Résumé :** Configurez le rôle serveur d’interopérabilité vidéo (a) dans Skype entreprise Server.
  
 Configurez les paramètres qui seront associés aux Trunks vidéo à l’aide de Windows PowerShell. Une configuration de Trunk vidéo avec étendue globale est créée une fois le service à l’aide de l’installation. Cette configuration de Trunk vidéo est appliquée par le biais de tous les Trunks qui n’ont pas de configuration de Trunk vidéo avec une étendue plus spécifique. Notez que la configuration de Trunk vidéo est une collection de paramètres applicables aux Trunks vidéo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurer le tronçon vidéo et le plan de numérotation

Utilisez les commandes Windows PowerShell suivantes pour spécifier la configuration de Trunk vidéo et le plan de numérotation à associer aux liaisons nouvellement définies définies dans le document topologique entre le VIS et toutes les passerelles vidéo. Tous ces paramètres sont configurables aux niveaux global, du site ou du service (passerelle vidéo). 
  
Un plan de numérotation avec étendue globale est créé par déploiement de Skype entreprise Server. Ce plan de numérotation est appliqué par tous les ISL qui n’ont pas de plan de numérotation ayant une étendue plus précise. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurer l’utilisation de Windows PowerShell

1. Créez une nouvelle configuration de Trunk vidéo (collection de paramètres) à utiliser sur le Trunk entre le directeur des communications unifiées (CallManager ou CUCM), à l’aide de l’applet de commande Windows PowerShell suivante :
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    S’il existe déjà un Trunk vidéo qui doit être modifié, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Pour afficher les paramètres associés à une configuration de Trunk vidéo particulière, utilisez l’applet de commande Windows PowerShell suivante :
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Pour supprimer une configuration de Trunk vidéo particulière, utilisez l’applet de commande Windows PowerShell suivante (Notez que la configuration de Trunk vidéo avec étendue globale) est appliquée si une configuration de Trunk vidéo de niveau supérieur n’est pas spécifiquement définie pour un Trunk particulier.
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Établissez un plan de numérotation à associer au Trunk, à l’aide des applets de commande Windows PowerShell suivantes :
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

La commande **Remove-CsVoiceNormalizationRule** est nécessaire pour remplacer une règle par défaut afin qu’elle n’interfère pas avec l’interaction CUCM ou du VIS attendue.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) peut être utilisé pour supprimer un plan de numérotation.
  
Dans le cas d’un appel vidéo en ligne SIP à partir d’une passerelle vidéo dont l’URI de la demande contient un numéro non-E. 164, l’accent lira le nom du plan de numérotation associé au Trunk associé et inclura le nom du plan de numérotation dans la partie contexte du téléphone de l’URI de la requête S envoie au premier plan. L’application de traduction sur le front end extrait et applique les règles de normalisation associées au plan de numérotation à l’URI de requête.
## <a name="trunk-configuration-options"></a>Options de configuration de tronçon

Les applets de décision Windows PowerShell pour la configuration de Trunk vidéo mentionnées précédemment étaient nouvelles dans Skype entreprise Server 2015. Les paramètres associés à la configuration de tronçon vidéo requièrent une brève explication.
  
 **GatewaySendsRtcpForActiveCalls** Ce paramètre détermine si les paquets RTCP sont envoyés à partir du VTC à l’envers pour les appels actifs. Un appel actif dans ce contexte désigne un appel qui est autorisé à voyager dans au moins une direction. Si le paramètre GatewaySendsRtcpForActiveCalls est défini sur True, le serveur d’interopérabilité vidéo (VIS) peut mettre fin à un appel s’il ne reçoit aucun paquet RTCP dans un délai de plus de 30 secondes. La valeur par défaut est **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Ce paramètre détermine si les paquets RTCP continuent d’être envoyés sur le Trunk pour les appels placés en attente et qu’aucun flux de paquets ne devait être acheminé dans chaque direction. Le serveur d’interopérabilité vidéo (VIS) peut mettre fin à l’appel s’il ne reçoit aucun paquet RTCP du système de vidéoconférence (VTC) lorsque l’appel est en attente. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableMediaEncryptionForSipOverTls** Ce paramètre active ou désactive SRTP pour le média lorsque le protocole SIPTransport est défini sur TLS. La valeur par défaut est **True**. Lorsque le protocole SIPTransport est défini sur TCP, ce paramètre est ignoré.
  
 **EnableSessionTimer** Ce paramètre active ou désactive les minuteurs de session à l’extrémité de chaque boîte de dialogue SIP associée au Trunk vidéo SIP. La valeur par défaut est **False**.
  
 **ForwardErrorCorrectionType** Ce paramètre est utilisé pour déterminer si la correction d’erreur de transfert (FEC) pour les flux vidéo doit être appliquée sur la jambe entre le serveur Video Interop et une passerelle vidéo. La définition de ForwardErrorCorrectionType sur « None » désactive la fonction FEC entre et la passerelle vidéo/VTC. La définition de ForwardErrorCorrectionType sur « Cisco » autorise la compatibilité FEC avec les passerelles vidéo de Cisco, telles que Cisco Unified Communications Manager (CUCM). La valeur par défaut est **Aucun**.
  
## <a name="see-also"></a>Voir aussi

[Configurer CUCM pour l’interopérabilité avec Skype entreprise Server](configure-cucm-for-interoperation.md)
