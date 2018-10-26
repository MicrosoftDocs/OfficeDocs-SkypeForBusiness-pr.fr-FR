---
title: 'Lync Server 2013 : Configuration des paramètres des comptes d’utilisateurs'
TOCTitle: Configuration des paramètres des comptes d’utilisateurs
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412896(v=OCS.15)
ms:contentKeyID: 49298635
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des paramètres des comptes d’utilisateurs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les utilisateurs d’appels entrants doivent entrer un numéro de téléphone ou de poste, ainsi qu’un code confidentiel pour participer à des conférences en qualité d’utilisateurs authentifiés. L’**URI de ligne** de téléphonie précisé dans les comptes d’utilisateurs Lync Server est requis à des fins d’authentification.

La procédure décrite dans cette rubrique explique comment affecter un **URI de ligne** pour un compte utilisateur unique. Si vous devez attribuer un **URI de ligne** à plusieurs comptes utilisateur, vous pouvez créer un script à l’aide de l’applet de commande **Set-CsUser**. Pour plus d’informations sur l’utilisation d’un exemple de script pour affecter un **URI de ligne** à plusieurs comptes utilisateur, reportez-vous à « Affecter des URI de ligne à plusieurs utilisateurs » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).

## Pour configurer les paramètres des comptes d’utilisateurs

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-UserAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans le champ de recherche, tapez le nom de l’utilisateur à configurer pour une conférence rendez-vous ou cliquez sur **Ajouter un filtre** pour spécifier les champs de la recherche, puis cliquez sur **Rechercher**.

5.  Double-cliquez sur le nom utilisateur pour ouvrir la boîte de dialogue **Modifier l’utilisateur Lync Server**.

6.  Sous **Téléphonie**, dans le champ **URI de ligne**, tapez un numéro de téléphone normalisé unique (par exemple, tel:+14255550200).
    
    > [!NOTE]  
    > Vous pouvez spécifier un <strong>URI de ligne</strong> uniquement si l’option <strong>Téléphonie</strong> est définie sur <strong>De PC à PC uniquement</strong>, <strong>Voix Entreprise</strong>, <strong>Contrôle d’appel distant</strong> ou <strong>Contrôle d’appel distant uniquement</strong>.

7.  Cliquez sur **Valider**.

