---
title: 'Lync Server 2013 : Octroi d’autorisations'
TOCTitle: Octroi d’autorisations
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398901(v=OCS.15)
ms:contentKeyID: 49298914
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Octroi d’autorisations dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-15_

En ce qui concerne l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique afin que les membres de ce groupe et de cette unité d’organisation puissent installer Lync Server 2013 dans le domaine spécifié. Quand vous octroyez des autorisations à une unité d’organisation, vous octroyez les autorisations suivantes :

  - Read

  - Write

  - ReadSPN

  - WriteSPN

En ce qui concerne l’administration, vous pouvez ajouter des autorisations aux unités d’organisation spécifiées afin que les membres des groupes universels RTC créés pendant la préparation de la forêt puissent y accéder sans avoir besoin d’appartenir au groupe Administrateurs du domaine. Les autorisations ajoutées à l’unité d’organisation spécifiée sont identiques à celles que l’applet de commande **Enable-CsAdDomain** ajoute aux conteneurs d’unités d’organisation d’ordinateurs et d’utilisateurs.

## Dans cette section

  - [Octroi d’autorisations de configuration dans Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Octroi d’autorisations d’unité organisationnelle dans Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

