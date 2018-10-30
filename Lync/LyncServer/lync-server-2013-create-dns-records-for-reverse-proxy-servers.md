---
title: "Lync Server 2013 : Créa. des enr. DNS pour les serveurs proxy inverses"
TOCTitle: Création des enregistrements DNS pour les serveurs proxy inverses
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429719(v=OCS.15)
ms:contentKeyID: 49298569
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création des enregistrements DNS pour les serveurs proxy inverses dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-29_

Créez des enregistrements DNS A externes pointant vers l’interface externe publique de votre serveur Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server ou Internet Information Server Application Request Routing, comme indiqué dans [Configuration de DNS pour la prise en charge de périphérie dans Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Ces enregistrements DNS sont nécessaires pour les noms de domaine complets de service web externe pour chaque pool, le directeur (ou pool de directeurs) et chaque URL simple.

Les enregistrements DNS minimum suivants doivent être créés pour la résolution client sur le proxy inverse :

  - Enregistrement hôte (A) qui définit les sites web externes publiés pour les directeurs et les pools de directeur (par exemple, **webdirext.contoso.com** )

  - Enregistrement hôte (A) qui définit les sites web externes publiés pour les services web externes hébergés sur les pools de serveurs frontaux et rôles serveur Standard Edition (par exemple, **webext.contoso.com** )

  - Enregistrement hôte (A) pour les URL simples (par exemple, **dialin.contoso.com** et **meet.contoso.com** )

  - Enregistrement hôte (A) pour l’enregistrement Lync Discover External ; fournit également un pointeur vers AutoDiscover pour toutes les applications web, notamment Lync Web App, le Planificateur et Mobilité (par exemple, **lyncdiscover.contoso.com** )

  - Enregistrement hôte (A) pour l’URL Office Web Apps Server (par exemple, **officewebapp01.contoso.com** )

Pour plus d’informations, reportez-vous à la section [Résumé DNS - Proxy inverse dans Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

