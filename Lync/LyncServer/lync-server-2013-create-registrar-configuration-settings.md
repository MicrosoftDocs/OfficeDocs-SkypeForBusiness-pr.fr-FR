---
title: Créer des paramètres de configuration d’un serveur d’inscriptions
TOCTitle: Créer des paramètres de configuration d’un serveur d’inscriptions
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182601(v=OCS.15)
ms:contentKeyID: 49299238
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Créer des paramètres de configuration d’un serveur d’inscriptions

 

_**Dernière rubrique modifiée :** 2013-03-17_

Vous pouvez utiliser le serveur d’inscriptions pour configurer les méthodes d’authentification du serveur proxy. Le protocole d’authentification que vous spécifiez détermine le type de difficultés que les serveurs du pool posent aux clients. Les protocoles disponibles sont :

  - **Kerberos**   Il s’agit du modèle d’authentification par mot de passe le plus puissant pour les clients, mais il est généralement mis à la disposition des clients entreprise uniquement parce qu’il exige une connexion client à un centre de distribution de clés (contrôleur de domaine Kerberos). Ce paramètre convient si le serveur doit uniquement authentifier des clients entreprise.

  - **NTLM**   Il s’agit de la solution d’authentification par mot de passe pour les clients qui appliquent un schéma de hachage stimulation/réponse au mot de passe. C’est la seule forme d’authentification proposée aux clients ne disposant pas d’une connectivité à un centre de distribution des clés (contrôleur de domaine Kerberos), tels que les utilisateurs distants. Si un serveur authentifie uniquement des utilisateurs distants, vous devrez choisir NTLM.

  - **Authentification par certificat**   Il s’agit de la nouvelle méthode d’authentification lorsque le serveur doit obtenir des certificats de clients Lync Phone Edition, de téléphones de partie commune et de Lync 2013. Sur des clients Lync Phone Edition, une fois qu’un utilisateur s’est connecté et authentifié au moyen de son code confidentiel, Lync Server 2013 fournit l’URI SIP au téléphone ainsi qu’un certificat Lync Server signé ou un certificat utilisateur qui identifie Jean (Ex : SN=jean@contoso.com) au téléphone. Ce certificat est utilisé pour l’authentification avec le serveur d’inscriptions et les services web.

> [!NOTE]  
> Nous vous recommandons d’activer Kerberos et NTLM lorsqu’un serveur prend à la fois en charge l’authentification des clients distants et d’entreprise. Le serveur Edge et les serveurs internes communiquent pour veiller à ce qu’une authentification NTLM seulement soit proposée aux clients distants. Si seul Kerberos est activé sur ces serveurs, ils ne peuvent pas authentifier les utilisateurs distants. Si des utilisateurs d’entreprise s’authentifient également envers le serveur, Kerberos est utilisé.

Procédez comme suit pour créer un nouveau serveur d’inscriptions.

## Pour créer un serveur d’inscriptions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Sur la page **Serveur d’inscriptions**, cliquez sur **Nouveau**.

5.  Dans **Sélectionner un service**, cliquez sur le service auquel le serveur d’inscriptions s’appliquera, puis cliquez sur **OK**.

6.  Dans **Nouveau paramètre de serveur d’inscriptions**, sélectionnez un ou plusieurs des éléments suivants selon les fonctionnalités des clients et la prise en charge de votre environnement :
    
      - **Activer l’authentification Kerberos** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification Kerberos.
    
      - **Activer l’authentification NTLM** pour que les serveurs du pool émettent des demandes à l’aide de l’authentification NTLM.
    
      - **Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.

7.  Cliquez sur **Valider**.

