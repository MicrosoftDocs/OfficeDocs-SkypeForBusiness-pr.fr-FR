---
title: "Lync Server 2013 : Conf. des itinéraires de comm. voc. pour appels sortants"
TOCTitle: Configuration des itinéraires de communications vocales pour les appels sortants
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425890(v=OCS.15)
ms:contentKeyID: 49296949
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Un itinéraire de communications vocales Lync Server 2013 associe des numéros de téléphone de destination à une ou plusieurs passerelles de réseau public commuté (RTC) ou jonctions SIP et un ou plusieurs enregistrements d’utilisation RTC.

**Pour afficher les itinéraires de communications vocales via Panneau de configuration Lync Server**

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Cliquez sur **Routage des communications vocales** .

3.  Cliquez sur **Itinéraire** .

4.  Double-cliquez sur un itinéraire de communications vocales pour afficher les autres propriétés de la liste des itinéraires de communications vocales ou sélectionnez l’itinéraire, puis cliquez sur **Modifier** . Cliquez ensuite sur **Afficher les détails** .
    
    > [!NOTE]  
    > Vous ne pouvez afficher les informations détaillées que d’un seul itinéraire à la fois.

**Afficher les itinéraires de communications vocales via Windows PowerShell**

  - Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**. Les itinéraires de communications vocales peuvent être affichés à l’aide de Windows PowerShell et de l’applet de commande **Get-CsVoiceRoute**. Il est possible d’exécuter cette dernière depuis le Lync Server 2013 Management Shell ou une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Pour afficher des informations sur tous vos itinéraires de communications vocales, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :
    
        Get-CsVoiceRoute
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

> [!NOTE]  
> Pour plus d’informations, reportez-vous à <a href="lync-server-2013-voice-routes.md">Itinéraires des communications vocales dans Lync Server 2013</a> dans la documentation de planification.

## Dans cette section

  - [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

## Voir aussi

#### Autres ressources

[Gestion du routage des communications vocales dans Lync Server 2013](lync-server-2013-managing-voice-routing.md)

