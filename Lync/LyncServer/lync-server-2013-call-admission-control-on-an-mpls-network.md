---
title: 'Lync Server 2013 : Contrôle d’admission des appels sur un réseau MPLS'
TOCTitle: Contrôle d’admission des appels sur un réseau MPLS
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398168(v=OCS.15)
ms:contentKeyID: 49296226
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’admission des appels sur un réseau MPLS avec Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Dans un réseau MPLS (Multiprotocol Label Switching), tous les sites sont connectés par un maillage. C’est-à-dire que tous les sites sont connectés directement au segment principal MPLS du fournisseur de services Internet, chaque site recevant la bande passante à utiliser sur une liaison de réseau étendu au cloud MPLS. Il n’y a aucun concentrateur réseau ou site central pour contrôler le routage IP. La figure suivante montre un réseau simple basé sur la technologie MPLS.

**Exemple de réseau MPLS**

![CAC avec MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC avec MPLS")

Pour déployer le contrôle d’admission des appels dans un réseau MPLS, vous devez créer une région sur le réseau pour représenter le cloud MPLS et créer un site réseau pour représenter chaque site satellite MPLS. La figure suivante montre comment la région et les sites du réseau doivent être configurés pour représenter le réseau MPLS exemple dans la figure précédente. Les limites globales de bande passante et de session de bande passante sont ensuite basées sur la capacité de la liaison de réseau étendu de chaque site vers la région qui représente le cloud MPLS.

**Région et sites d’un réseau MPLS**

![Diagramme de contrôle d’admission des appels (CAC) avec MPLS](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Diagramme de contrôle d’admission des appels (CAC) avec MPLS")

