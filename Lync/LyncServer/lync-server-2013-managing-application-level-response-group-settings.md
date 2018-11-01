---
title: "Gest. des param. de Response Group au niveau de l’app. dans Lync Server 2013"
TOCtitle: "Gest. des param. de Response Group au niveau de l’app. dans Lync Server 2013"
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49891486
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des paramètres de Response Group au niveau de l’application dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les paramètres de niveau application pour l’application Response Group incluent la configuration de la mise en attente musicale, le fichier audio de mise en attente musicale par défaut, la période de grâce de reprise d’appel parqué d’agent et la configuration du contexte de l’appel. Vous pouvez définir un seul jeu de paramètres de niveau application par pool. Pour afficher les paramètres de niveau application, utilisez l’applet de commande **Get-CsRgsConfiguration**. Pour modifier les paramètres de niveau application, utilisez l’applet de commande **Set-CsRgsConfiguration**.

L’attente musicale par défaut est lue lorsqu’un appel est mis en attente uniquement si aucune attente musicale personnalisée n’est définie. Le contexte de l’appel est disponible uniquement pour les files d’attentes assignées à des flux de travail interactifs. Si le contexte de l’appel est activé, un agent peut afficher des informations telles que le délai d’attente de l’appelant ou des questions et réponses de flux de travail lorsqu’un appel est reçu.

## Pour modifier les paramètres de niveau application de Response Group

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante :
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    Par exemple :
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    Pour spécifier un fichier audio à utiliser comme attente musicale par défaut, vous devez d’abord importer le fichier audio. Par exemple :
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

## Voir aussi

#### Autres ressources

[Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-CsRgsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)

