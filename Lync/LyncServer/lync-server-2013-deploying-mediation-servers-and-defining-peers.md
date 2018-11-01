---
title: "Lync Server 2013 : Dépl. des serveurs de médiation et déf. des homologues"
TOCTitle: Déploiement des serveurs de médiation et définition des homologues
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412780(v=OCS.15)
ms:contentKeyID: 49298443
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des serveurs de médiation et définition des homologues dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

La charge de travail Voix Entreprise, la conférence rendez-vous et les applications Voix Entreprise avancées ( application Response Group, application de parcage d’appel, contrôle d’admission des appels, et ainsi de suite) sont disponibles dans les pools de serveurs frontaux. Avec Lync Server 2013, la fonctionnalité du serveur de médiation est intégrée au serveur frontal. Un serveur de médiation autonome distinct n’est plus nécessaire. Les pools de serveurs frontaux peuvent communiquer directement avec les passerelles prises en charge (une passerelle RTC \[Public Switched Telephone Network\] ou un système IP-PBX), évitant ainsi de faire appel à un serveur de médiation en guise d’intermédiaire.

La seule exception est si vous configurez une jonction SIP pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour connecter votre infrastructure Voix Entreprise à votre fournisseur de jonctions SIP, vous devez déployer un serveur de médiation distinct.

La connexion entre Lync Server (le composant serveur de médiation sur un pool de serveurs frontaux ou serveur de médiation autonome) et une passerelle est définie en tant qu’association logique appelée *jonction* . Les rubriques de cette section décrivent comment définir une jonction et déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.

## Dans cette section

  - [Définition d’un serveur de médiation dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Définition d’une passerelle dans le générateur de topologie dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Installation des fichiers du serveur de médiation dans Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Définition d’autres jonctions dans le Gestionnaire de topologies dans Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

## Sections connexes

[Configuration de conférences rendez-vous dans Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

