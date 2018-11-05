---
title: Suppression d’une annonce
TOCTitle: Suppression d’une annonce
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49891272
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une annonce

 

_**Dernière rubrique modifiée :** 2012-11-01_

Procédez de la façon suivante pour supprimer une annonce utilisée pour passer des appels à des numéros non attribués.

## Pour supprimer une annonce

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé, en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires tels que décrits dans [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsAnnouncement

4.  Dans la liste obtenue, recherchez l’annonce que vous voulez supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Par exemple :
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    > [!NOTE]  
    > Pour plus d’informations sur d’autres options, voir <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</a>.

## Voir aussi

#### Tâches

[Création d’une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)  

#### Autres ressources

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)

