---
title: Gestion des groupes d’agents Response Group
TOCTitle: Gestion des groupes d’agents Response Group
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520976(v=OCS.15)
ms:contentKeyID: 49296849
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des groupes d’agents Response Group

 

_**Dernière rubrique modifiée :** 2012-10-01_

Un groupe d’agents est un groupe de personnes désignées pour répondre aux appels d’un groupe de réponses. Lorsque vous créez un groupe d’agents, vous sélectionnez les agents assignés au groupe et spécifiez divers autres paramètres du groupe. Vous pouvez ainsi sélectionner la méthode de routage des appels et définir si un agent peut se connecter à un groupe et s’en déconnecter.

> [!NOTE]  
> Pour ajouter des utilisateurs à des groupes d’agents, ils doivent être activés pour Voix Entreprise. Pour plus d’informations sur l’activation des utilisateurs pour Voix Entreprise, voir <a href="lync-server-2013-enable-users-for-enterprise-voice.md">Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013</a>.

> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent local passe en ligne, les appels Response Group ne sont pas acheminés vers lui.

Un agent qui doit se connecter au groupe et s’en déconnecter (différent de la connexion à Lync Server et de la déconnexion de celui-ci) est appelé *agent formel*. Les agents formels doivent être connectés au groupe pour recevoir des appels acheminés vers le groupe. Cela peut être utile pour les agents qui répondent à temps partiel aux appels du groupe. Les agents formels se connectent à leur groupe et s’en déconnectent en cliquant sur un élément de menu dans Lync 2013 pour ouvrir le navigateur Windows Internet Explorer et afficher une console web.

Un agent qui ne doit pas se connecter au groupe ou s’en déconnecter est appelé *agent informel*. Ces agents se connectent automatiquement au groupe lorsqu’ils se connectent à Lync Server. Ils ne peuvent pas se déconnecter du groupe.

> [!IMPORTANT]  
> Lorsque vous affectez des utilisateurs en tant qu’agents au groupe de réponses, informez-les que, s’ils ont activé le mode de confidentialité, ils doivent rechercher des contacts « RGS Presence Watcher » et les ajouter à leur liste de contacts. Les agents qui ont activé le mode confidentiel mais qui ne disposent pas de contacts « RGS Presence Watcher » dans leur liste de contacts, ne peuvent pas recevoir d’appels. Cela ne concerne pas les agents qui n’ont pas activé le mode de confidentialité.

## Dans cette section

  - [Création ou modification d’un groupe d’agents dans Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Supprimer un groupe d’agents](lync-server-2013-delete-an-agent-group.md)

