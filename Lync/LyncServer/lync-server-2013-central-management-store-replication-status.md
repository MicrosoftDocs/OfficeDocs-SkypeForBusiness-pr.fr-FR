---
title: "Skype Entreprise Server 2015 : statut de réplic. du magasin central de gest."
TOCTitle: Statut de réplication du magasin central de gestion
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn720926(v=OCS.15)
ms:contentKeyID: 62240071
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Statut de réplication du magasin central de gestion dans Skype Entreprise Server 2015

 

_**Dernière rubrique modifiée :** 2015-01-26_

Lorsqu’un administrateur apporte une modification quelconque à Lync Server (par exemple, lorsqu’il crée une stratégie de voix ou modifie les paramètres de configuration du serveur de carnet d’adresses), cette modification est enregistrée dans le magasin central de gestion. Elle doit ensuite être répliquée sur tous les ordinateurs qui exécutent des services ou des rôles de serveur Lync Server.

Pour répliquer des données, le réplicateur principal (exécuté sur le serveur central de gestion) crée un instantané des données de configuration modifiées. Une copie de cet instantané est alors envoyée à chaque ordinateur qui exécute des services ou des rôles de serveur Lync Server. Sur ces ordinateurs, un agent de réplication reçoit l’instantané et transfère les données modifiées. L’agent envoie ensuite au réplicateur principal un message signalant le dernier statut de réplication.

L’applet de commande Get-CsManagementStoreReplicationStatus permet de vérifier le statut de réplication d’un ordinateur (ou de tous les ordinateurs) Lync Server dans votre organisation.

Qui peut exécuter cette applet de commande ? Par défaut, les membres des groupes ci-dessous ont l’autorisation d’exécuter localement l’applet de commande Get-CsManagementStoreReplicationStatus : RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Pour renvoyer une liste de tous les rôles de contrôle d’accès basé sur les rôles (RBAC) auxquels cette applet de commande a été affectée (dont les rôles RBAC personnalisés que vous avez créés), exécutez la commande ci-après à partir de l’invite de Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

## Voir aussi

#### Autres ressources

[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsManagementStoreReplicationStatus)

