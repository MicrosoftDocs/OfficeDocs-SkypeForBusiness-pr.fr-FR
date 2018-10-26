---
title: 'Lync Server 2013 : Création ou modification d’un site réseau'
TOCTitle: Création ou modification d’un site réseau
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398218(v=OCS.15)
ms:contentKeyID: 49296347
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’un site réseau dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-24_

Les déploiements du contrôle d’admission des appels, du système E9-1-1 et de la déviation du trafic multimédia s’appuient sur la configuration des *sites réseau* définis dans une région du réseau et toujours associés à celle-ci. Un site réseau représente un site de succursale, un ensemble de bâtiments ou un campus d’université. Les sites réseau représentent des ensembles de sous-réseaux avec une bande passante similaire.

Les procédures suivantes vous permettent de créer ou de modifier des sites réseau. Par exemple, si vous avez créé des sites réseau pour une fonctionnalité vocale, vous n’avez pas besoin de créer d’autres sites réseau ; les autres fonctionnalités vocales utiliseront ces mêmes sites. Cependant, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.

> [!NOTE]  
> Vous pouvez trouver des exemples et des conditions spécifiques pour les sites réseau concernant chaque fonctionnalité vocale avancée dans la documentation de déploiement :<ul>
> <li><p><a href="lync-server-2013-configure-network-sites-for-cac.md">Configurer les sites réseau pour le contrôle d’admission des appels dans Lync Server 2013</a></p></li></ul>


Pour plus d’informations sur l’utilisation des sites réseau, reportez-vous à la documentation de Lync Server Management Shell pour les applets de commande suivantes :

  - [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)

## Créer un site réseau

Créez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia.

## Pour créer un site réseau à l’aide de Lync Server Management Shell

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Exemple :
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica » (Amérique du Nord).
    
    > [!NOTE]  
    > La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.

3.  Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

## Pour créer un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** .

3.  Cliquez sur le bouton de navigation **Site** .

4.  Cliquez sur **Nouveau** .

5.  Dans la page **Nouveau site** , cliquez sur **Nom** , puis tapez le nom du site réseau.

6.  Cliquez sur **Région** , puis cliquez sur une région dans la liste.

7.  Éventuellement, cliquez sur **Stratégie de bande passante** , puis sur une stratégie de bande passante dans la liste.
    
    > [!NOTE]  
    > La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site.

8.  Éventuellement, cliquez sur **Stratégie d’emplacement** , puis sur une stratégie d’emplacement dans la liste.
    
    > [!NOTE]  
    > La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site.

9.  Éventuellement, cliquez sur **Description** , puis tapez des informations supplémentaires pour décrire ce site réseau.

10. Cliquez sur **Valider** .

11. Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.

## Modifier un site réseau

Modifiez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia.

## Pour modifier un site réseau

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :
    
        Set-CsNetworkSite -Identity <string>
    
    Exemple :
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    Dans cet exemple, le site appelé « Albuquerque » est déplacé dans la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.
    
    > [!NOTE]  
    > Même si le paramètre BypassID existe pour la déviation du trafic multimédia, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour la déviation du trafic multimédia.

3.  Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.

## Pour modifier un site réseau à l’aide du Panneau de configuration Lync Server

1.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** .

3.  Cliquez sur le bouton de navigation **Site** .

4.  Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.

5.  Cliquez sur **Modifier** , puis sur **Afficher les détails…** .

6.  Dans la page **Modifier le site** , changez les valeurs des paramètres de ce site réseau comme il convient.

7.  Cliquez sur **Valider** .

8.  Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.

