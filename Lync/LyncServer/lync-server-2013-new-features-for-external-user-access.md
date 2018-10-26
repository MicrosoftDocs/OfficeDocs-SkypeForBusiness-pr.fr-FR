---
title: "Lync Server 2013 : Nlles fonct. liées à l’accès des ut. Ext."
TOCTitle: Nouvelles fonctionnalités liées à l’accès des utilisateurs externes
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398794(v=OCS.15)
ms:contentKeyID: 49298272
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nouvelles fonctionnalités liées à l’accès des utilisateurs externes dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-17_

Lync Server 2013 présente de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication offertes aux utilisateurs. Par ailleurs, Lync Server 2013 apporte des modifications à certains services existants afin de mieux intégrer et d’élargir les services disponibles dans votre organisation. Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur vos opérations de planification et de déploiement des services fournis par le serveur Edge  Lync Server 2013.

  - **Prise en charge de l’adressage IPv6**     Lync Server 2013 prend en charge de l’adressage IPv6 pour tous les services serveur Edge. Si vous avez fourni des adresses IPv6 pour les interfaces par le biais de la configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge par le biais de la configuration d’adresse IP dans le Générateur de topologie.
    
    > [!IMPORTANT]  
    > L’utilisation d’adresses IPv6 dans Lync Server 2013 dépend de la prise en charge du protocole IPv6 dans les routeurs et pare-feu déployés par votre organisation, ainsi que de la prise en charge offerte par votre fournisseur de services Internet.

  - **Extensible Messaging and Presence Protocol (XMPP)**     Lync Server 2013 offre un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux. Vous pouvez déployer la fédération XMPP en tant que composant facultatif. L’ajout et la configuration du proxy XMPP et de la passerelle XMPP permettront à vos utilisateurs Microsoft Lync 2013 d’ajouter des contacts de partenaires XMPP pour la messagerie instantanée et la présence.
    
    > [!NOTE]  
    > Actuellement, les services XMPP dans Lync Server 2013 fournissent uniquement la messagerie instantanée et la présence entre les clients Lync et les contacts XMPP.

  - **Services de mobilité pour les clients mobiles**    Introduits dans une mise à jour du client pour Lync Server 2010, les services de mobilité dans Lync Server 2013 permettent aux clients Microsoft Lync Mobile sur téléphones mobiles et tablettes utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge d’effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. Par ailleurs, les appareils mobiles prennent en charge certaines fonctionnalités de Voix Entreprise telles que Cliquez pour rejoindre une conférence, Appel via le bureau, Appel de numéro unique, la messagerie vocale et la notification d’appel en absence.
    
    > [!NOTE]  
    > Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux. Aucune modification des serveurs Edge n’est requise.

  - Les **directeurs sont un rôle facultatif**    Le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé. Il héberge toujours les services web, pré-authentifie les demandes utilisateur entrantes et dirige les utilisateurs externes vers leur d’accueil. Le changement du directeur d’un rôle recommandé en un rôle facultatif n’atténue pas la valeur du directeur, mais souligne la réduction du nombre de serveurs et d’autres exigences matérielles (par exemple, l’équilibrage de la charge matérielle pour le directeur) sans compromettre l’efficacité des fonctionnalités. Étant donné que les serveurs frontaux peuvent faire le même travail que le directeur sans aucun impact sur les services fournis, vous pouvez si vous le souhaitez déployer des directeurs. Vous pouvez sans risque exclure le directeur en étant confiant que les serveurs frontaux procureront les mêmes services à sa place.

## Voir aussi

#### Concepts

[Planification et configuration d’IPv6 dans Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  

#### Autres ressources

[Planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planification de la fédération XMPP (Extensible Messaging and Presence Protocol) dans Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)

