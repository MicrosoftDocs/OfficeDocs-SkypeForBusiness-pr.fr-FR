---
title: 'Lync Server 2013 : Fonctionnalités de mobilité'
TOCTitle: Fonctionnalités de mobilité
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh689983(v=OCS.15)
ms:contentKeyID: 49296312
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fonctionnalités de mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 de février 2013 permet de prendre en charge des fonctions des clients Lync 2010 Mobile et Lync 2013 Mobile. Lorsque vous déployez le service de mobilité Lync Server 2013, les utilisateurs peuvent employer les appareils mobiles Apple iOS, Android, Windows Phone ou Nokia Symbian pris en charge pour s’adonner à des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence. En outre, les appareils mobiles prennent en charge certaines fonctionnalités Voix Entreprise, telles que le clic pour participer à une conférence, l’appel via le bureau, le numéro unique, la messagerie vocale et les appels manqués. Parmi les nouvelles fonctionnalités introduites dans les mises à jour cumulatives pour Lync Server 2013 de février 2013 figurent la fonctionnalité VoIP et la vidéo (H.264) pour les participants aux réunions.

La fonctionnalité de mobilité introduite dans les mises à jour cumulatives pour Lync Server 2013 de février 2013 permet de prendre en charge des fonctions du client Lync 2013 Mobile. Les mises à jour cumulatives pour Lync Server 2013 de février 2013 installent l’API UCWA (Unified Communications Web API). Celle-ci est le composant utilisé pour les clients Lync 2013 Mobile. Dans Lync Server 2013, Mcx est utilisé pour les clients Lync 2010 Mobile. Les mises à jour cumulatives pour Lync Server 2013 de février 2013 introduisent l’API UCWA comme nouveau point d’entrée des services de mobilité. Parallèlement, Lync Server 2013 implémente le service de mobilité (Mcx), introduit dans les mises à jour cumulatives pour Lync Server 2010 de novembre 2011 et fournit la prise en charge de Lync 2010 Mobile. Quand vous déployez les mises à jour cumulatives pour Lync Server 2013 de février 2013, les utilisateurs peuvent utiliser les appareils mobiles Apple iOS, Android et Windows Phone pris en charge pour effectuer des activités telles que les suivantes :

> [!IMPORTANT]  
> Les fonctionnalités prises en charge par le service de mobilité à partir des mises à jour cumulatives pour Lync Server 2010 de novembre 2011 portent la mention « (Mcx) ». Toutes les fonctionnalités répertoriées sont prises en charge par l’API UCWA, introduite dans les mises à jour cumulatives pour Lync Server 2013 de février 2013.

  - Envoyer et recevoir des messages instantanés (Mcx)

  - Afficher les informations de présence (Mcx)

  - Afficher les contacts (Mcx)

  - Cliquer pour participer à une conférence (Mcx)

  - Appeler via le bureau (Mcx)

  - Numéro unique (Mcx)

  - Messagerie vocale (Mcx)

  - Notification des appels manqués (Mcx)

  - VoIP

  - Vidéo des participants (H.264)

> [!NOTE]  
> Lync 2010 Mobile fournissait un client pour les appareils Nokia Symbian. Pour sa part, Lync 2013 Mobile ne possédera pas de client pour les appareils reposant sur Nokia Symbian.

Les utilisateurs d’appareils Apple iPad auront accès aux fonctionnalités améliorées. Après avoir rejoint une réunion par appel audio, un utilisateur d’appareil iPad pourra consulter les présentations Microsoft PowerPoint téléchargées dans une réunion, partager les applications et les bureaux, afficher la liste des participants à la réunion et recevoir des notifications d’autres types de contenu partagés dans le cadre de la réunion.

> [!TIP]  
> Grâce au numéro unique, un utilisateur reçoit les appels qui ont été passés en composant son numéro professionnel sur son téléphone portable. L’appel via le bureau permet à l’utilisateur de passer un appel sortant à partir du client Lync Mobile en utilisant un numéro professionnel au lieu du numéro du téléphone portable. Avec la mise en conférence par téléphone, le client envoie une demande au service Mcx ou à l’API UCWA (suivant la Lync Mobile) afin qu’il effectue l’appel. Le serveur lance l’appel, puis rappelle l’utilisateur sur son téléphone mobile. Quand ce dernier répond, le serveur termine l’appel en composant le numéro de l’interlocuteur. L’utilisation de l’appel via le bureau permet aux utilisateurs de conserver leur identité professionnelle pendant un appel, ce qui signifie que le destinataire de l’appel ne voit pas le numéro de portable de l’appelant, et ce dernier évite ainsi les frais d’appel sortant encourus.

> [!NOTE]  
> Les fonctionnalités ne fonctionnent pas toutes de la même manière sur les appareils mobiles. Pour plus d’informations sur les fonctionnalités prises en charge sur ce type d’appareil, reportez-vous aux tableaux de comparaison des clients mobiles à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</a>. Pour plus d’informations sur les appareils et les systèmes d’exploitation pris en charge, reportez-vous aux rubriques liées aux exigences sous <a href="lync-server-2013-planning-for-mobile-clients.md">Planification des clients mobiles dans Lync Server 2013</a>.

Quand vous utilisez la fonctionnalité de découverte automatique Lync Server 2013, les applications mobiles peuvent rechercher automatiquement les services web Lync Server 2013 sans demander aux utilisateurs d’entrer manuellement les URL correspondantes dans les paramètres de leur appareil. La saisie manuelle des URL dans les paramètres d’un appareil mobile est également prise en charge, principalement à des fins de résolution des problèmes.

> [!IMPORTANT]  
> Le service Mcx et l’API UCWA sont des services gratuits et sont tous deux déployés pour prendre en charge les clients Lync 2010 Mobile et Lync 2013 Mobile. Lync 2013 Mobile ne sera pas en mesure de se connecter aux déploiements Lync Server 2010. Lync 2010 Mobile et Lync 2013 Mobile pourront utiliser un déploiement Lync Server 2013 auquel auront été appliquées les mises à jour cumulatives pour Lync Server 2013 de février 2013.

La fonctionnalité de mobilité prend également en charge les *notifications push* pour les appareils mobiles qui ne prennent pas en charge les applications qui s’exécutent en arrière-plan. Une notification push est une notification envoyée à un appareil mobile à propos d’un événement qui se produit pendant qu’une application mobile n’est pas active. Une invitation par messagerie instantanée manquée est un exemple d’événement qui entraîne une notification push.

Le service Mcx, l’API UCWA, le service de découverte automatique et la prise en charge des notifications push sont fournis dans Lync Server 2013. Les fonctionnalités clientes mises à jour, les fonctions et l’utilisation de l’API UCWA comme point d’entrée pour la mobilité sont introduites dans les mises à jour cumulatives pour Lync Server 2013 de février 2013.

