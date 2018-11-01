---
title: Importation des stratégies et des paramètres
TOCTitle: Importation des stratégies et des paramètres
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205178(v=OCS.15)
ms:contentKeyID: 49298558
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importation des stratégies et des paramètres

 

_**Dernière rubrique modifiée :** 2012-09-28_

Une fois que vous avez fusionné les informations relatives à votre topologie Office Communications Server 2007 R2 avec votre pool pilote Lync Server 2013, vous devez exécuter une applet de commande Lync Server 2013 Management Shell pour migrer vos stratégies et paramètres de configuration Office Communications Server 2007 R2 vers votre pool pilote Lync Server 2013.

L’applet de commande **Import-CsLegacyConfiguration** importe les stratégies, les itinéraires des communications vocales, les plans de numérotation, les URL d’Office Communicator Web Access et les numéros d’accès entrant de Lync Server 2013 vers nm-ocs-14-2nd.

## Pour migrer les stratégies et les paramètres

1.  Sur le serveur frontal Lync Server 2013, démarrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Import-CsLegacyConfiguration
    
    Une fois que les stratégies sont importées, utilisez la procédure suivante pour afficher les stratégies importées dans le Panneau de configuration Lync Server.

## Pour afficher les stratégies importées

1.  Ouvrez le Panneau de configuration Lync Server 2013.

2.  Cliquez sur **Routage des communications vocales** et affichez les stratégies importées.

3.  Cliquez sur **Conférence** et affichez les stratégies importées.

4.  Cliquez sur **Fédération et accès externe** et affichez les stratégies importées.

5.  Cliquez sur **Surveillance et archivage** et affichez les stratégies importées.

