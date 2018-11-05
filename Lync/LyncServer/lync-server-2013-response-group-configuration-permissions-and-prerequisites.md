---
title: "Lync Server 2013 : Aut. et cond. prérequises pour la conf. de Response Group"
TOCTitle: Autorisations et conditions prérequises pour la configuration de Response Group
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204840(v=OCS.15)
ms:contentKeyID: 49297026
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Response Group est une fonctionnalité de gestion des appels Voix Entreprise. Cette rubrique décrit ce dont vous avez besoin pour configurer Response Group, ainsi que les autorisations et les informations d’identification d’administrateur nécessaires à la réalisation des tâches de configuration.

Cette section suppose que vous avez lu la documentation de planification se rapportant à Response Group. Pour plus d’informations, reportez-vous à [Planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) dans la documentation de planification.

## Outils de configuration et rôles d’administrateur

Vous pouvez utiliser les outils d’administration suivants pour configurer Response Group :

  - Panneau de configuration Lync Server

  - outil de configuration Response Group

  - Lync Server Management Shell

Pour configurer les groupes Response Group, vous devez être membre d’au moins un des rôles d’administrateur suivants :


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Groupe de sécurité Active Directory (1)</strong></p></td>
<td><p>Créer un flux de travail</p></td>
<td><p>Affecter un responsable</p></td>
<td><p>Créer/affecter des agents, files d’attente</p></td>
<td><p>Créer/gérer des vacances et heures d’ouverture</p></td>
<td><p>Activer/désactiver un flux de travail</p></td>
<td><p>Configurer un flux de travail (réponse vocale interactive ou groupe de recherche)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>v(2)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> <strong>(1)</strong> Un objet utilisateur services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié. Un administrateur ou autre membre de groupe Active Directory délégué disposant des autorisations nécessaires pour ajouter des utilisateurs à un groupe de sécurité (par exemple, Administrateur, Opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité mentionné pour que l’utilisateur puisse exécuter les fonctions indiquées. <strong>(2)</strong> Uniquement pour les flux de travail que le groupe CsResponseGroupAdministrator a affectés au groupe CsResponseGroupManager. <strong>(3)</strong> Un responsable Response Group peut affecter un autre membre du groupe CsResponseGroupManager à un flux de travail dont le responsable actuel a déjà la charge. <strong>(4)</strong> Le groupe CsViewOnlyAdministrator peut uniquement exécuter les applets de commande Lync Server Management Shell avec le verbe « Get ».

## Composants requis pour la configuration de Response Group

Response Group requiert les composants suivants :

  - service d’application

  - application Response Group

  - Modules linguistiques

  - Magasin de fichiers (pour conserver les fichiers audio)

  - Services web (inclut l’outil de configuration Response Group et la console de connexion et de déconnexion de l’agent)

Tous ces composants sont installés par défaut lorsque vous déployez Voix Entreprise.

Vous serez peut-être amené à effectuer les tâches suivantes avant de configurer Response Group :

  - activer les utilisateurs pour Lync Server 2013 et Voix Entreprise ;

  - modifier un fichier de configuration pour être compatible avec les normes FIPS (Federal Information Processing Standard) ;

  - modifier le classement de base de données afin de prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents.

## Activation des utilisateurs

La première étape de configuration de Response Group consiste à créer des groupes d’agents. Pour pouvoir créer un groupe d’agents, vous devez d’abord activer les utilisateurs destinés à devenir agents de Response Group pour Lync Server 2013 et Voix Entreprise. L’activation des utilisateurs pour Lync Server 2013 est généralement une étape du déploiement d’un serveur Enterprise Edition ou Standard Edition. Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, reportez-vous à [Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). L’activation des utilisateurs pour Voix Entreprise est généralement une étape du déploiement de Voix Entreprise. Pour plus d’informations, reportez-vous à [Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

## Mise en conformité avec les normes FIPS

Cette section vous est applicable uniquement si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).

Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés. Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage. Pour le application Response Group, cette exigence s’applique à l’outil de configuration Response Group et à la console de connexion et de déconnexion de l’agent. Pour plus d’informations sur cette exigence, reportez-vous à l’article 911722 de la base de connaissances Microsoft, « Vous pouvez recevoir un message d’erreur en accédant à des pages web ASP.NET sur lesquelles l’état d’affichage est activé après la mise à niveau d’ASP.NET 1.1 vers ASP.NET 2.0 » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183).

Pour modifier le fichier Web.config, procédez comme suit :

1.  Dans un éditeur de texte tel que le Bloc-Notes, ouvrez le fichier d’application Web.config.

2.  Dans le fichier Web.config, recherchez la section `<system.web>`.

3.  Ajoutez la section `<machineKey>` ci-dessous dans la section `<system.web>` :
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Enregistrez le fichier Web.config.

5.  Redémarrez les services Internet (IIS) en exécutant la commande suivante dans une invite de commande :
    
        iisreset

## Prise en charge des caractères Yi, Meng et Zang

Cette section vous est applicable seulement si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.

> [!NOTE]  
> Pour plus d’informations sur les caractères Yi, Meng et Zang et pour savoir en quoi ils sont essentiels à votre déploiement, reportez-vous au document relatif aux jeux de caractères GB18030 à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</a>.

Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux suivants dans chaque base de données Rgsconfig :

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le classement Latin\_General\_100 (respect des accents). Si vous utilisez ce classement, certains noms d’objet ne respectent pas la casse.

Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outiil, reportez-vous à « Utilisation de SQL Server Management Studio » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184). Pour modifier le classement, procédez comme suit :

1.  Assurez-vous que SQL Server Management Studio est configuré pour autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, reportez-vous à « Boîte de dialogue Enregistrer (non autorisé) » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186). Pour plus d’informations sur le classement des colonnes, reportez-vous à « Procédure : définir le classement des colonnes (Visual Database Tools) » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185).

2.  À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.

3.  Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**.

4.  Modifiez le classement de la colonne **Nom** et enregistrez la table.

