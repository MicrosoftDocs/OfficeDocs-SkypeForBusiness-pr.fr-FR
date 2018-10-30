---
title: Supprimer une plage de numéros de prise d’appel de groupe
TOCTitle: Supprimer une plage de numéros de prise d’appel de groupe
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945629(v=OCS.15)
ms:contentKeyID: 53095422
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une plage de numéros de prise d’appel de groupe

 

_**Dernière rubrique modifiée :** 2013-01-30_

La procédure suivante vous permet de supprimer une plage de numéros de prise d’appel de groupe.

## Pour supprimer une plage de numéros de groupe de prise d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Sur la ligne de commande, tapez :
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    Exemple :
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    > [!NOTE]  
    > Pour plus d’informations sur d’autres options, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>.

## Voir aussi

#### Tâches

[Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Autres ressources

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

