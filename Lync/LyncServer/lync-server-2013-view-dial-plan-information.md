---
title: Affichage des informations d’un plan de numérotation dans Lync Server 2013
TOCTitle: Affichage des informations d’un plan de numérotation dans Lync Server 2013
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49891269
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des informations d’un plan de numérotation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Pour afficher les informations d’un plan de numérotation existant, effectuez la procédure suivante. Pour créer un plan de numérotation, voir [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

## Pour afficher les informations d’un plan de numérotation à partir de Panneau de configuration Lync Server

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4.  Dans la page **Plan de numérotation**, double-cliquez sur le nom du plan de numérotation.
    
    > [!NOTE]  
    > Vous ne pouvez afficher les informations que d’un seul plan de numération à la fois.

## Affichage de plans de numérotation à l’aide des applets de commande Windows PowerShell

  - Les plans de numérotation peuvent également être affichés à l’aide de interface de ligne de commande Windows PowerShell et de l’applet de commande **Get-CsDialPlan**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Pour afficher des informations sur tous vos plans de numérotation, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsDialPlan
    
    Les informations renvoyées par cette commande se présentent ainsi :
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## Voir aussi

#### Tâches

[Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

