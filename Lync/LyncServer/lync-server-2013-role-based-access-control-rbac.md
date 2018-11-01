---
title: Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013
TOCTitle: Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013
ms:assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481134(v=OCS.15)
ms:contentKeyID: 59679145
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’accès basé sur un rôle (RBAC) pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

Microsoft Lync Server 2013 inclut des groupes RBAC (Contrôle d’accès basé sur un rôle) pour vous permettre de déléguer les tâches d’administration tout en maintenant des normes élevées en matière de sécurité. Ces groupes sont créés durant la préparation de la forêt. Pour plus d’informations sur la préparation de la forêt, voir [Services de domaine Active Directory pour Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md). Pour plus d’informations sur les groupes spécifiques créés par la préparation de la forêt, voir [Modifications effectuées par la préparation de la forêt dans Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) dans la documentation de déploiement.

Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis, incluant les 11 rôles prédéfinis qui couvrent de nombreuses tâches d’administration courantes. Chaque rôle est associé à une liste spécifique d’applets de commande Lync Server Management Shell que les utilisateurs dans ce rôle sont autorisés à exécuter. Vous pouvez utiliser le contrôle d’accès basé sur un rôle pour suivre le principe du « privilège minimum » qui limite les droits d’administration octroyés aux utilisateurs à ceux nécessaires à leur travail. Pour plus d’informations, voir [Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) dans la documentation de planification.

