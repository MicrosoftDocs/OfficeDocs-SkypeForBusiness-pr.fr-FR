---
title: Associer des sous-réseaux à des sites réseau pour CAC
TOCTitle: Associer des sous-réseaux à des sites réseau pour CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412786(v=OCS.15)
ms:contentKeyID: 49298436
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Associer des sous-réseaux à des sites réseau pour CAC

 

_**Dernière rubrique modifiée :** 2012-10-20_

Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique. Ceci est dû au fait que les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un point de terminaison. Lorsque les emplacements des deux parties dans une session sont connus, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir un appel.

Le contrôle d’admission des appels ne présente aucune exigence particulière quant à l’association des sous-réseaux aux sites réseau. Pour créer une association entre des sous-réseaux et des sites réseau dans votre topologie, suivez les procédures décrites dans [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md). Pour voir les sites réseau (et leurs sous-réseaux respectifs) dans l’exemple de topologie réseau pour le contrôle d’admission des appels, voir l’exemple [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.

