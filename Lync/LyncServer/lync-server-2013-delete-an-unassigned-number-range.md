---
title: Supprimer une plage de numéros non attribués dans Lync Server 2013
TOCTitle: Supprimer une plage de numéros non attribués dans Lync Server 2013
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182565(v=OCS.15)
ms:contentKeyID: 49298471
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Supprimer une plage de numéros non attribués dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Appliquez l’une des procédures suivantes pour supprimer une plage de numéros non attribués pour des annonces.

## Pour supprimer une plage de numéros non attribués à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Fonctionnalités vocales**, puis sur **Numéro non attribué**.

4.  Dans la page **Numéro non attribué**, dans le champ recherche, tapez entièrement ou partiellement le nom de la plage de numéros non attribués que vous voulez supprimer.

5.  Dans la liste des plages de numéros résultante, cliquez sur le nom, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **Tout valider**.

## Pour supprimer une plage de numéros non attribués à l’aide d’applets de commande

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Sur la ligne de commande, tapez :
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Par exemple :
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    > [!NOTE]  
    > Pour plus d’informations sur d’autres options, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>.

## Voir aussi

#### Tâches

[Création ou modification d’une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### Autres ressources

[Remove-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

