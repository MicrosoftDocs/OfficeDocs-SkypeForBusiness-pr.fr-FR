---
title: 'Lync Server 2013 : Windows Update pour Lync Server'
TOCTitle: Windows Update pour Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518337(v=OCS.15)
ms:contentKeyID: 60484539
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows Update pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-12-05_

Recherchez fréquemment les mises à jour et les mises à jour de sécurité avec le service Windows Update et appliquez-les. Cette opération contribue à empêcher les vulnérabilités dans d’autres composants du système, qui peuvent permettre à des attaquants d’accéder aux serveurs exécutant Microsoft Lync Server 2013 avec des droits d’administrateur et ainsi compromettre Lync Server 2013.

Les mises à jour de Microsoft SQL Server 2008 Express (édition 64 bits) sont exécutées sur chaque serveur Lync Server 2013 Standard Edition (pour la base de données d’arrière-plan) et sur tous les autres serveurs de rôle Lync Server 2013 (pour le magasin de configuration local) sauf si vous avez mis ces bases de données à niveau vers SQL Server 2008 V2 Express. Vous devez prendre en compte ces bases de données dans le cadre de la maintenance de routine des mises à jour de sécurité, comme SQL Server dans la base de données d’arrière-plan, la base de données de surveillance et la base de données d’archivage.

## Meilleures pratiques

  - Restez à jour avec Windows Update.

