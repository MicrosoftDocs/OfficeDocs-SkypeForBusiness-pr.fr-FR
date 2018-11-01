---
title: 'Lync Server 2013 : Contrôle d’admission des appels et serveur de médiation'
TOCTitle: Contrôle d’admission des appels et serveur de médiation
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398585(v=OCS.15)
ms:contentKeyID: 49297781
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Le contrôle d’admission des appels (CAC), nouveauté dans Lync Server 2010, gère l’établissement de session en temps réel en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité de l’expérience (QoE) pour les utilisateurs sur des réseaux saturés. Pour prendre en charge cette fonctionnalité, le serveur de médiation, qui fournit la signalisation et la conversion des médias entre l’infrastructure Voix Entreprise et une passerelle ou un fournisseur de jonction SIP, est responsable de la gestion de la bande passante pour ses deux interactions du côté Lync Server et du côté passerelle. Dans le cadre du contrôle d’admission des appels, l’entité qui met fin à l’appel gère la réservation de la bande passante. Les homologues de passerelle (passerelle RTC, IP-PBX, SBC) avec lesquels interagit le serveur de médiation du côté passerelle ne prennent pas en charge le contrôle d’admission des appels Lync Server 2013. Par conséquent, le serveur de médiation doit gérer les interactions de bande passante de la part de son homologue de passerelle. À chaque fois que cela est possible, le serveur de médiation réserve la bande passante à l’avance. Si c’est impossible (par exemple, si la localité du point de terminaison final du média du côté passerelle est inconnue pour un appel sortant vers l’homologue de passerelle), la bande passante est réservée quand l’appel est passé. Ce comportement peut entraîner une sur-souscription de bande passante, mais c’est le seul moyen d’empêcher les sonneries factices.

La déviation du trafic multimédia et la réservation de bande passante s’excluent mutuellement. Si la déviation du trafic multimédia est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel. L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel. Si le contrôle d’admission des appels est utilisé pour un appel en particulier qui implique le serveur de médiation, cet appel ne peut pas se servir de la déviation du trafic multimédia.

Pour plus d’informations sur la déviation du trafic multimédia ou le contrôle d’admission des appels, reportez-vous à [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) ou à [Planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.

