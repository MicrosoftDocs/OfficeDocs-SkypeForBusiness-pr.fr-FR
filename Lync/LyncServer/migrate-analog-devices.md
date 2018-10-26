---
title: Migration des appareils analogiques
TOCTitle: Migration des appareils analogiques
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49891487
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des appareils analogiques

 

_**Dernière rubrique modifiée :** 2012-10-16_

Lync Server prend en charge des périphériques analogiques. Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques. Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation de périphériques analogiques dans votre environnement Lync Server. Après avoir migré de Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets contact associés aux périphériques analogiques. Utilisez Lync Server Management Shell pour d’abord récupérer tous les objets contact associés aux périphériques analogiques Lync Server 2010, puis déplacez ces objets vers le pool Lync Server 2013.

## Pour migrer des périphériques analogiques

1.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Dans la ligne de commande, tapez :
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  Vérifiez que tous les objets contact ont été déplacés vers le pool Lync Server 2013. Dans la ligne de commande, tapez :
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  Vérifiez que tous les objets contact sont maintenant associés au pool Lync Server 2013.

