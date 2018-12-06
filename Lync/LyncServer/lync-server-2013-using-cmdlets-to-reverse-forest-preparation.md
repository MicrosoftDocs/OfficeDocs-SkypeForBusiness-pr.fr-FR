---
title: 'Lync Server 2013 : Utilisation des commandes d’applet pour inverser la préparation d’une forêt'
TOCTitle: Utilisation des commandes d’applet pour inverser la préparation d’une forêt
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413024(v=OCS.15)
ms:contentKeyID: 49299367
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation des commandes d’applet pour inverser la préparation d’une forêt pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-06-19_

Utilisez l’applet de commande **Disable-CsAdForest** pour inverser la procédure de préparation d’une forêt.

> [!CAUTION]  
> Si vous exécutez l’applet de commande <strong>Disable-CsAdForest</strong> dans un environnement où une version précédente de Lync Server est déployée, les paramètres globaux de la version précédente seront également supprimés.

## Pour utiliser des applets de commande afin d’inverser la préparation d’une forêt

1.  Ouvrez une session sur un ordinateur associé à un domaine en tant que membre du groupe Administrateurs du domaine dans le domaine racine de la forêt.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Exemple :
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Le paramètre Force spécifie s’il faut forcer l’exécution de la tâche. Si ce paramètre n’est pas présent, la commande ne s’exécutera pas si même un domaine de la forêt est encore préparé pour Lync Server 2013. Si le paramètre Force est spécifié, l’action se poursuit quel que soit l’état des autres domaines dans la forêt.
    
    Si vous omettez le paramètre GroupDomain, le domaine local est utilisé par défaut.

## Voir aussi

#### Tâches

[Exécution de la préparation de la forêt pour Lync Server 2013](lync-server-2013-running-forest-preparation.md)  

#### Autres ressources

[Préparation de la forêt pour Lync Server 2013](lync-server-2013-preparing-the-forest.md)

