---
title: "Lync Server 2013 : Héb. des ut. sur un SBA ou un SBS"
TOCTitle: Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413066(v=OCS.15)
ms:contentKeyID: 49299427
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-12-10_

Le processus d’hébergement des utilisateurs sur Survivable Branch Appliance ou un serveur Survivable Branch Server est identique au processus d’hébergement des utilisateurs sur un pool de serveurs frontaux. Effectuez la procédure Survivable Branch Appliance ou serveur Survivable Branch Server sur le site central.

## Pour héberger des utilisateurs sur un Survivable Branch Appliance ou sur un serveur Survivable Branch Server

1.  Avant de déplacer les utilisateurs vers le serveur Survivable Branch Server ou le serveur Survivable Branch Server, ouvrez Lync Server Management Shell, puis effectuez toutes les opérations suivantes :
    
      - Exécutez l’applet de commande **Test-CsPstnOutboundCall** pour vérifier que le serveur Survivable Branch Server s’exécute et que la connectivité du réseau téléphonique commuté (RTC) est configurée. Si vous avez besoin de modifier les propriétés de la passerelle RTC, utilisez la **Set-CsPstnGateway**.
    
      - Exécutez l’applet de commande **Get-CsVoicePolicy** pour vérifier que les utilisateurs qui seront hébergés sur le serveur Survivable Branch Server disposent de la stratégie de routage VoIP qui convient. Si vous avez besoin de modifier la stratégie VoIP, utilisez l’applet de commande **Set-CsVoicePolicy**.
    
      - Exécutez la **Get-CsVoicemailReroutingConfiguration** pour vérifier que les paramètres de réacheminement de la messagerie vocale sont configurés. Si vous avez besoin de modifier les paramètres de réacheminement de la messagerie vocale, utilisez l’applet de commande **Set-CsVoicemailReroutingConfiguration**.

2.  Dans Lync Server Management Shell, exécutez l’applet de commande **Move-CsUser** pour héberger des utilisateurs.

> [!NOTE]  
> Vous pouvez également utiliser le Panneau de configuration Lync Server pour vérifier les conditions préalables et héberger les utilisateurs.

## Voir aussi

#### Autres ressources

[Test-CsPstnOutboundCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnOutboundCall)  
[Get-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoicemailReroutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsUser)

