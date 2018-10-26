---
title: "Personnalis. de l’attente musicale du parcage d’appels dans Lync Server 2013"
TOCtitle: "Personnalis. de l’attente musicale du parcage d’appels dans Lync Server 2013"
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49891317
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Personnalisation de l’attente musicale du parcage d’appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-10_

Vous pouvez spécifier un fichier de musique personnel à utiliser en guise d’attente musicale en lieu et place du fichier de musique par défaut fourni avec Lync Server 2013. Pour personnaliser l’attente musicale, utilisez l’applet de commande **Set-CsCallParkServiceMusicOnHoldFile**.

> [!NOTE]  
> Si vous personnalisez l’attente musicale et voulez utiliser la même musique pour plusieurs sites, vous devez configurer le fichier de musique pour chaque site exécutant l’application de parcage d’appel.

## Pour personnaliser le fichier de musique

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    > [!TIP]  
    > Utilisez l’applet de commande <strong>Get-CsService</strong> pour identifier le service. Pour plus d’informations, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService">Get-CsService</a>.    
    L’exemple suivant montre comment obtenir le contenu d’un fichier (soothingmusic.wma) sous la forme d’un tableau d’octets et l’affecter à une variable. Le fichier audio est ensuite affecté au fichier d’attente musicale du parcage d’appel. Pour plus d’informations, voir [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

## Voir aussi

#### Autres ressources

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[Get-CsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsService)

