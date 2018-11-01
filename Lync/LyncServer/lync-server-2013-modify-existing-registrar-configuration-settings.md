---
title: "Modif. des paramètres de configuration d’un serveur d’inscriptions existant"
TOCtitle: "Modif. des paramètres de configuration d’un serveur d’inscriptions existant"
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182566(v=OCS.15)
ms:contentKeyID: 49298453
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Modification des paramètres de configuration d’un serveur d’inscriptions existant

 

_**Dernière rubrique modifiée :** 2012-11-01_

Vous pouvez utiliser le serveur d’inscriptions pour configurer les protocoles d’authentification du serveur proxy. Pour plus d’informations sur les protocoles disponibles, voir [Créer des paramètres de configuration d’un serveur d’inscriptions](lync-server-2013-create-registrar-configuration-settings.md).

> [!NOTE]  
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.

Procédez comme suit pour modifier un serveur d’inscription existant.

## Pour modifier un serveur d’inscription existant

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Dans la page **Serveur d’inscriptions**, cliquez sur un service, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier le paramètre du serveur d’inscriptions**, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
      - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
      - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.

6.  Cliquez sur **Valider**.

