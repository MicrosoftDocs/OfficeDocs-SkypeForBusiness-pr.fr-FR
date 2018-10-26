---
title: Migration des téléphones en zone commune
TOCTitle: Migration des téléphones en zone commune
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49891295
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migration des téléphones en zone commune

 

_**Dernière rubrique modifiée :** 2012-09-29_

Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour délivrer la fonctionnalité de communications unifiées Lync Server. Une fois effectuée la migration d’un déploiement Lync Server 2010 vers Lync Server 2013, vous devez également transférer les objets contact associés au téléphone de partie commune hérité. Dans Lync Server Management Shell, vous récupérez d’abord les objets contact associés aux téléphones de partie commune Lync Server 2010, puis vous déplacer ces objets vers le pool Lync Server 2013.

**Migration des téléphones de partie commune**

1.  Sur le serveur frontal Lync Server 2013, ouvrez Lync Server Management Shell.

2.  Dans la ligne de commande, tapez ce qui suit :
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  Pour vérifier que tous les objets contact ont été déplacés vers le pool Lync Server 2013, dans Lync Server Management Shell tapez la commande suivante :
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    Vérifiez que tous les objets contact sont désormais associés au pool Lync Server 2013.

