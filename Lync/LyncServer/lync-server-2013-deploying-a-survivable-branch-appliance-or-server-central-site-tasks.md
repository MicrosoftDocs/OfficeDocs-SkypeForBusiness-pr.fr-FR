---
title: "Lync Server 2013 : Dépl. d’un SBA ou d’un SBS - Tâches pour un site central"
TOCTitle: Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server - Tâches pour un site central
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398189(v=OCS.15)
ms:contentKeyID: 49296271
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013 - Tâches pour un site central

 

_**Dernière rubrique modifiée :** 2012-10-18_

Effectuez les tâches de cette section sur le site central. Si vous déployez un serveur Survivable Branch Server, ignorez la première tâche.

> [!IMPORTANT]  
> Avant d’effectuer les tâches dans cette section, les conditions suivantes doivent être remplies :
> <ul>
> <li><p>Lync Server doit être installé sur le site central.</p></li>
> <li><p>Un technicien d’installation du site de succursale doit être ajouté au groupe RTCUniversalSBATechnicians.</p></li></ul>
> En outre, nous vous recommandons d’effectuer ce qui suit :
> <ul>
> <li><p>Déployez un serveur DHCP sur chaque site de succursale pour permettre aux clients d’obtenir les adresses IP.</p></li>
> <li><p>Outre le déploiement d’un serveur DHCP sur chaque site de succursale, vous pouvez activer le serveur DHCP Lync Server sur le Survivable Branch Appliance ou serveur Survivable Branch Server via l’applet de commande Lync Server Management Shell<strong>Set-CsRegistrarConfiguration –EnableDHCPServer $true</strong>. Pour plus d’informations, reportez-vous à la secton liée au matériel et aux logiciels requis de <a href="lync-server-2013-branch-site-resiliency-requirements.md">Configuration requise pour la résistance des sites de succursale pour Lync Server 2013</a> dans la documentation de planification.</p></li></ul>


## Dans cette section

  - [Ajout d’un Survivable Branch Appliance à Active Directory dans Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Ajout des sites de succursale à votre topologie dans Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Définition d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server dans Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

