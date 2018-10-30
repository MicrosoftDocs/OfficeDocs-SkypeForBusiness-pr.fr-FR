---
title: Modification des URL simples après la migration
TOCTitle: Modification des URL simples après la migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49891488
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des URL simples après la migration

 

_**Dernière rubrique modifiée :** 2012-09-22_

Lync Server prend en charge trois URL simples :

  - **Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation. Avec l’URL simple de réunion, les liens pour participer à des réunions sont faciles à comprendre, à communiquer et à distribuer.

  - **Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous. L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.

  - **Admin** qui permet un accès rapide au Panneau de configuration Lync Server. L’URL simple Admin est interne à votre organisation.

Après avoir migré vers Lync Server 2013, vous devez savoir dans quelle mesure cette modification risque d’altérer les enregistrements et les certificats DNS (Domain Name System) pour les URL simples. Si le directeur Lync Server 2010 hérité continue à être utilisé dans la topologie, aucune modification de vos URL simples n’est requise. Si le directeur Lync Server 2010 est supprimé de la topologie après la migration, les enregistrements DNS des URL simples doivent être mis à jour pour pointer vers l’un des pools Lync Server 2013. Cependant, lorsque vous modifiez le nom d’une URL simple, vous devez exécuter Enable-CsComputer sur chaque directeur et serveur frontal pour enregistrer la modification.

## Modification des URL simples après la migration

**Pour mettre à jour l’URL simple Meet**

1.  Dans le Générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **Modifier les propriétés** .

2.  Sélectionnez **URL simples** dans le volet gauche, et sous **URL de réunion :** , sélectionnez l’URL Meet, puis cliquez sur **Modifier l’URL** .

3.  Mettez à jour l’URL avec la valeur voulue, puis cliquez sur **OK** pour l’enregistrer.

**Pour mettre à jour l’URL simple Admin**

1.  Dans le Générateur de topologie, cliquez avec le bouton droit sur le nœud supérieur **Lync Server**, puis cliquez sur **Modifier les propriétés** .

2.  Sélectionnez **URL simples** dans le volet gauche, et sous la zone **URL d’accès administratif** , entrez l’URL simple souhaitée pour un accès administratif au Panneau de configuration Lync Server 2013, puis cliquez sur **OK** .
    
    > [!TIP]  
    > Nous vous recommandons d’utiliser l’URL la plus simple possible pour l’URL Admin. L’option la plus simple est <strong>https://admin.</strong> <em>&lt;domain&gt;</em> .

## Voir aussi

#### Concepts

[Planification des URL simples dans Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

