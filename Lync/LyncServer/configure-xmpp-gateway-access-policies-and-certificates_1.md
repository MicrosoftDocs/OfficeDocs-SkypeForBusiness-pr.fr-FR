---
title: Configuration des stratégies d’accès et des certificats de la passerelle XMPP
TOCTitle: Configuration des stratégies d’accès et des certificats de la passerelle XMPP
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49891547
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies d’accès et des certificats de la passerelle XMPP

 

_**Dernière rubrique modifiée :** 2012-10-15_

La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (Extensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs Lync d’accéder aux utilisateurs de domaine XMPP en utilisant :

  - Messagerie instantanée et présence – de personne à personne uniquement

  - Création de contacts fédérés XMPP dans le client Lync

Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole XMPP, les stratégies s’appliquent aux utilisateurs des domaines XMPP fédérés, mais pas aux utilisateurs des fournisseurs de service de messagerie instantanée par protocole SIP (par exemple, Windows Live), ou les domaines fédérés SIP. Configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP pour chaque domaine XMPP fédéré avec lequel vos utilisateurs pourront communiquer et ajouter des contacts. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.

> [!NOTE]  
> Pour commencer la migration de la passerelle XMPP, vous devez déployer la passerelle XMPP Lync Server 2013, puis configurer les stratégies d’accès pour activer les utilisateurs sur la passerelle XMPP Lync Server 2013. Tous les utilisateurs doivent être déplacés vers le déploiement Lync Server 2013 avant de procéder à ces étapes. Pour plus d’informations, reportez-vous à <a href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configuration de la passerelle XMPP sur Lync Server 2013</a>.

## Configuration d’une stratégie d’accès externe pour activer les utilisateurs pour la passerelle XMPP Lync Server 2013

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis cliquez sur **Stratégie d’accès externe**.

3.  Cliquez sur **Nouveau** puis sur **Stratégie utilisateur**.

4.  Entrez un nom pour la stratégie utilisateur d’accès externe.

5.  Fournissez une description pour la stratégie utilisateur d’accès externe

6.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés**.

7.  Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.

8.  Cliquez sur **Valider** pour enregistrer vos modifications du site ou de la stratégie de l’utilisateur.

