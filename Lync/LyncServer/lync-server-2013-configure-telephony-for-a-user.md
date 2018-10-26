---
title: Configuration de la téléphonie pour un utilisateur
TOCTitle: Configuration de la téléphonie pour un utilisateur
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520988(v=OCS.15)
ms:contentKeyID: 49297061
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la téléphonie pour un utilisateur

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les paramètres de téléphonie font partie des paramètres individuels d’un compte d’utilisateur que vous pouvez définir dans le Panneau de configuration Lync Server pour l’utilisateur (si ce dernier a été activé pour Lync Server 2013 et que l’organisation prend en charge la téléphonie).

Les options de téléphonie utilisateur Lync Server incluent les éléments suivants :

  - **Audio/vidéo désactivé**   L’utilisateur ne peut pas passer d’appels avec de l’audio et de la vidéo.

  - **De PC à PC uniquement**   L’utilisateur peut seulement passer des appels audio ou vidéo de PC à PC.

  - **Voix Entreprise**   L’utilisateur peut se servir de l’infrastructure Lync Server 2013 pour acheminer tous les appels entrants et sortants. L’utilisateur peut aussi effectuer des appels de PC à PC.

  - **Contrôle d’appel distant**   L’utilisateur peut se servir de Lync Server 2013 pour contrôler le téléphone de bureau et peut aussi passer des appels de PC à PC.

Pour plus d’informations sur la configuration de la téléphonie dans une organisation, voir [Configuration de la téléphonie pour un utilisateur](lync-server-2013-configure-telephony-for-a-user.md) et [Déploiement de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.

## Pour configurer la téléphonie pour un compte d’utilisateur spécifique

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.

6.  Dans le menu **Edition**, cliquez sur **Modifier**.

7.  Dans **Téléphonie**, procédez comme suit :
    
      - Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.
    
      - Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou Voix Entreprise, cliquez sur **De PC à PC uniquement**. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.
    
      - Pour router les appels téléphoniques de l’utilisateur via l’infrastructure Lync Server 2010 conformément à la stratégie de classe de service, dont la communication audio de PC à PC, cliquez sur **Voix Entreprise**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise. Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur. Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.
    
      - Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne téléphonique de bureau depuis Lync Server 2013, afin de passer des appels de PC à PC et des appels de PC à téléphone, cliquez sur **Contrôle d’appel distant**. Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant. L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.

## Voir aussi

#### Autres ressources

[Modification des propriétés d’un compte d’utilisateur](lync-server-2013-modifying-user-account-properties.md)

