---
title: Vérification des informations de topologie
TOCTitle: Vérification des informations de topologie
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205151(v=OCS.15)
ms:contentKeyID: 49298475
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vérification des informations de topologie

 

_**Dernière rubrique modifiée :** 2012-09-26_

La première étape de la procédure de vérification de la fusion consiste à afficher les informations de la topologie Office Communications Server 2007 R2 que vous avez fusionnées avec Lync Server 2013. Dans le générateur de topologie, le nœud **BackCompatSite** affiche le nom de domaine complet de chaque pool et serveur Office Communications Server 2007 R2 que vous avez fusionnés.

## Pour afficher BackCompatSite dans le générateur de topologie

1.  Dans votre environnement Office Communications Server 2007 R2, ouvrez l’outil d’administration Office Communications Server 2007 R2 et notez les noms de domaine complets des pools et serveurs hérités.

2.  Dans votre environnement Lync Server 2013, ouvrez le générateur de topologie, puis développez le nœud **BackCompatSite** .

3.  Vérifiez que les noms de domaine complets des pools et serveurs que vous fusionnez sont affichés.
    
    > [!NOTE]  
    > Aucune information n’est affichée dans <strong>BackCompatSite</strong> pour les rôles serveur colocalisés sur un serveur frontal ou un serveur Standard Edition. Seuls les rôles serveur nécessaires à l’interopérabilité entre Office Communications Server 2007 R2 et Lync Server 2013 sont affichés.

![Boîte de dialogue BackCompatSite du Générateur de topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Boîte de dialogue BackCompatSite du Générateur de topologie")

Vous pouvez également utiliser le Panneau de configuration Lync Server 2013 pour afficher votre topologie fusionnée. Dans le Panneau de configuration Lync Server 2013, vous pouvez voir le nom de domaine complet de chaque serveur, celui de chaque pool et le nom de site de votre topologie fusionnée. Les serveurs fusionnés porte le nom de **Site** **BackCompatSite** .

## Pour afficher la topologie fusionnée dans Panneau de configuration Lync Server 2013

1.  Ouvrez le Panneau de configuration Lync Server 2013.

2.  Cliquez sur **Topologie** .

3.  Sous l’onglet **Statut** , vérifiez que les serveurs et pools que vous avez fusionnés s’affichent en recherchant **BackCompatSite** dans la colonne **Site** .

![Panneau de configuration Lync Server montrant la fusion de topologie](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Panneau de configuration Lync Server montrant la fusion de topologie")

Pour afficher plus d’informations sur un pool fusionné, utilisez l’applet de commande **Get-CsPool** . Outre les informations disponibles dans le générateur de topologie et le Panneau de configuration Lync Server 2013, cette applet de commande affiche les services qui s’exécutent sur le pool Lync Server 2013.

> [!NOTE]  
> Lorsque vous publiez la topologie après avoir exécuté l’Assistant Fusion dans le générateur de topologie, les annuaires des conférences sont fusionnés à Lync Server 2013. Les annuaires des conférences peuvent être vérifiés en exécutant l’applet de commande <strong>Get-CsConferenceDirectory</strong>.

## Pour afficher les services sur un pool fusionné

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    Exemple :
    
        Get-CsPool -Identity pool02.contoso.net

## Pour vérifier les annuaires des conférences fusionnés

1.  Ouvrez Lync Server 2013 Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsConferenceDirectory

3.  Vérifiez que tous les annuaires des conférences pour le pool ou serveur que vous fusionnez figurent désormais dans Lync Server 2013.

