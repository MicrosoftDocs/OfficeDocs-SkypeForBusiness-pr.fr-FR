---
title: Création d’un périphérique pour tester la fonctionnalité de mise à jour
TOCTitle: Création d’un périphérique pour tester la fonctionnalité de mise à jour
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182587(v=OCS.15)
ms:contentKeyID: 49298900
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’un périphérique pour tester la fonctionnalité de mise à jour

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez ajouter un périphérique de test à la page **Périphérique de test**, puis l’utiliser pour vérifier la fonctionnalité des nouvelles mises à jour avant de les déployer sur des périphériques de production. Vous pouvez tester un périphérique globalement (dans tout votre environnement Lync Server) ou sur un site unique. Vous identifiez un périphérique de test grâce à son adresse MAC (Media Access Control) ou son numéro de série. Lorsque vous ajoutez un périphérique, son nom apparaît dans la liste de la page **Périphérique de test** du Panneau de configuration Lync Server.

## Pour ajouter un périphérique de test

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Périphérique de test**.

3.  Cliquez sur **Nouveau**, puis sur **Périphérique de test global** ou **Périphérique de test sur site**.

4.  Effectuez l’une des opérations suivantes :
    
      - Si vous avez cliqué sur **Périphérique de test global**, passez à l’étape suivante.
    
      - Si vous avez cliqué sur **Périphérique de test sur site**, sélectionnez un site dans la liste des sites disponibles, puis cliquez sur **OK**.

5.  Dans **Nouveau périphérique de test**, tapez un nom de périphérique dans **Nom du périphérique**.

6.  Sous **Type d’identificateur**, cliquez sur **Adresse MAC** ou **Numéro de série**.

7.  Dans la zone **Identificateur unique**, tapez l’adresse MAC ou le numéro de série du périphérique.

8.  Cliquez sur **Valider**.

## Création de périphériques de test à l’aide d’applets de commande Windows PowerShell

Les périphériques de test peuvent également être créés à l’aide de Windows PowerShell et de l’applet de commande New-CsTestDevice. Cette dernière peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

Lors de la création de périphériques de test à l’aide de cette applet de commande, vous devez effectuer deux opérations :

  - spécifier MACAddress ou SerialNumber comme IdentifierType ;

  - inclure l’étendue lorsque vous spécifiez l’identité du périphérique. Pour créer un périphérique au niveau global, utilisez une syntaxe telle que celle-ci :
    
        -Identity "global/WindowsPhone"
    
    Pour créer un périphérique de test au niveau de l’étendue Site, utilisez une syntaxe semblable à celle-ci :
    
        -Identity "site:Redmond/WindowsPhone"

## Pour créer un périphérique de test à l’aide de l’adresse MAC

  - Cette commande crée un périphérique de test au niveau de l’étendue Site et utilise l’adresse MAC comme IdentifierType :
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

## Pour créer un périphérique de test à l’aide du numéro de série

  - Cette commande crée un périphérique de test au niveau de l’étendue Site (pour le site Redmond) et utilise le numéro de série comme IdentifierType :
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

Pour plus d’informations, voir la rubrique d’aide associée à l’applet de commande [New-CsTestDevice](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTestDevice).

