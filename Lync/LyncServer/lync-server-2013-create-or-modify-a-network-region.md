﻿---
title: 'Lync Server 2013 : Création ou modification d’une région réseau'
TOCTitle: Création ou modification d’une région réseau
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412933(v=OCS.15)
ms:contentKeyID: 49298694
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une région réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-19_

Les *régions réseau* sont les concentrateurs réseau ou dorsales principales utilisées dans la configuration du contrôle d’admission des appels, du service E9-1-1 et de la déviation du trafic multimédia. Les procédures suivantes vous permettent de créer ou de modifier des régions réseau. Par exemple, si vous avez déjà créé des régions réseau pour une fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau ; d’autres fonctionnalités Voix Entreprise avancées utiliseront ces mêmes régions. Cependant, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central. Pour plus d’informations, reportez-vous à [Configurer les régions de réseau pour le contrôle d’admission des appels (CAC)](lync-server-2013-configure-network-regions-for-cac.md).

> [!NOTE]  
> Toutes les exigences ayant trait à des fonctionnalités pour les définitions des régions réseau sont documentées dans les rubriques de déploiement des fonctionnalités concernées.

Pour plus d’informations sur l’utilisation des régions réseau, reportez-vous à la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)

## Créer une région réseau

Créez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia.

## Pour créer une région réseau à l’aide du Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Exemple :
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    Dans cet exemple, vous avez créé une région réseau appelée « NorthAmerica » (Amérique du Nord) associée à un site central avec l’ID de site CHICAGO.

3.  Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.

## Pour créer une région réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** .

3.  Cliquez sur **Région** .

4.  Cliquez sur **Nouveau** .

5.  Dans la page **Nouvelle région** , cliquez sur **Nom** , puis tapez le nom de la région réseau.

6.  Cliquez sur **Site central** , puis cliquez sur un site central dans la liste.

7.  Éventuellement, cliquez sur **Description** , puis tapez des informations supplémentaires pour décrire ce site réseau.

8.  Cliquez sur **Valider** .

9.  Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.

## Modifier une région réseau

Modifiez les paramètres d’une région réseau existante pour gérer les changements apportés aux informations de base sur les régions ou les changements requis dans le cadre d’une nouvelle fonctionnalité.

## Pour modifier une région réseau à l’aide du Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Exemple :
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    Dans cet exemple, vous avez modifié une région réseau existante appelée « NorthAmerica » (créée en suivant les procédures décrites plus haut dans cette rubrique) en changeant sa description. Si une description existait dans la région « NorthAmerica », cette commande la remplace par cette valeur. Si aucune description n’a été définie, cette commande s’en charge.

3.  Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.

## Pour modifier une région réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** .

3.  Cliquez sur le bouton de navigation **Région** .

4.  Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.

5.  Cliquez sur **Modifier** , puis sur **Afficher les détails…** .

6.  Dans la page **Modifier la région** , changez les valeurs des paramètres de cette région réseau comme il convient.

7.  Cliquez sur **Valider** .

8.  Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.

