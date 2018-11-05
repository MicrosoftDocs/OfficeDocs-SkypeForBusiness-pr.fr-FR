---
title: Assigner des stratégies à un téléphone de partie commune
TOCTitle: Assigner des stratégies à un téléphone de partie commune
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994082(v=OCS.15)
ms:contentKeyID: 53095562
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Assigner des stratégies à un téléphone de partie commune

 

_**Dernière rubrique modifiée :** 2013-02-20_

Après avoir créé votre stratégie pour les téléphones de partie commune (pour plus d’informations, voir [Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), vous pouvez assigner la stratégie à un téléphone de partie commune en utilisant Windows PowerShell et l’applet de commande **Grant-Cs** appropriée. Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une sessions à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).


## Affectation d’une stratégie à un téléphone de partir commune

  - La commande suivante assigne la stratégie voix par utilisateur RedmondVoice au téléphone de partie commune avec Identity Building 14 Lobby.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

## Affectation d’une stratégie à plusieurs téléphones de partie commune

  - Dans cet exemple, la stratégie voix par utilisateur RedmondVoice est assignée à tous les téléphones de partie commune utilisés au sein de l’organisation.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

Pour plus d’informations, voir les rubriques d’aide relatives à [Grant-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsVoicePolicy).

## Voir aussi

#### Autres ressources

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

