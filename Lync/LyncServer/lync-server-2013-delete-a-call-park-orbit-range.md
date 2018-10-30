---
title: Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013
TOCTitle: Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182546(v=OCS.15)
ms:contentKeyID: 49297955
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une plage d’orbites de parcage d’appel dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-20_

Utilisez l’une des procédures suivantes pour supprimer une plage d’orbites de parcage d’appel.

## Pour utiliser le Panneau de configuration Lync Server pour supprimer une plage d’orbites de parcage d’appel

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Parcage d’appel**.

4.  Dans la page **Parcage d’appel**, dans le champ recherche, tapez entièrement ou partiellement le nom de la plage d’orbites à supprimer.

5.  Dans la liste d’orbites qui en résulte, cliquez sur l’orbite, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

## Pour utiliser les applets de commande pour supprimer une plage d’orbites de parcage d’appel

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Sur la ligne de commande, tapez :
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    Par exemple :
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    > [!NOTE]  
    > Pour plus d’informations sur d’autres options, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>.

## Voir aussi

#### Tâches

[Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### Autres ressources

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

