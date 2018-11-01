---
title: Afficher la liste des applications approuvées
TOCTitle: Afficher la liste des applications approuvées
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182604(v=OCS.15)
ms:contentKeyID: 49299309
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Afficher la liste des applications approuvées

 

_**Dernière rubrique modifiée :** 2012-09-21_

Le Panneau de configuration Lync Server 2013 permet de consulter la liste des applications approuvées déployées dans votre environnement Lync Server 2013. Une application approuvée est une application basée sur un Kit de développement logiciel (SDK) d’API managée Microsoft Unified Communications (UCMA) 3.0 Core approuvé par Lync Server 2013. Cette relation de confiance est récapitulée dans la liste suivante :

  - Lync Server ne requiert pas l’authentification des applications approuvées.

  - Les applications approuvées ne sont pas limitées par Lync Server pour les transactions SIP, les connexions ou des appels VoIP (protocole voix sur IP) sortants.

  - Les applications approuvées peuvent emprunter l’identité de n’importe quel utilisateur et participer à des conférences sans apparaître dans les listes.

  - Les applications approuvées sont hautement disponibles et résistantes.

Panneau de configuration Lync Server affiche le nom des applications, le pool dans lequel elles s’exécutent et le port qu’elles utilisent.

## Pour consulter la liste des applications approuvées

1.  À partir d’un compte d’utilisateur auquel est affecté un rôle d’administrateur CsServerAdministrator, CsAdministrator, CsHelpDesk ou CsViewOnlyAdministrator pour Lync Server 2013, ouvrez une session sur un ordinateur de votre déploiement interne. Pour plus de détails sur les rôles d’administrateur prédéfinis disponibles dans Lync Server 2013, voir [Planification du contrôle d’accès basé sur un rôle dans Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **Application approuvée**.

4.  Sur la page **Application approuvée**, cliquez sur l’en-tête d’une colonne pour trier les applications, si nécessaire.

## Voir aussi

#### Autres ressources

[Gestion de la topologie Lync Server 2013](lync-server-2013-managing-the-lync-server-topology.md)

