---
title: "Lync Server 2013 : Proc. de prép. et de dépl. d’un env. hybride Lync Server"
TOCTitle: Procédure de préparation et de déploiement d’un environnement hybride Lync Server 2013
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205157(v=OCS.15)
ms:contentKeyID: 49298409
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Procédure de préparation et de déploiement d’un environnement hybride Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le tableau ci-dessous répertorie les étapes requises pour préparer votre environnement pour un déploiement hybride avec Microsoft Lync Online et Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Terminé ?</th>
<th>Étape</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p>Créer un compte client pour Office 365 et activer Lync Online</p></td>
<td><p>Découvrez Office 365 et Lync Online sur le site web d’<a href="http://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</p>
<p>Pour vérifier que votre environnement est prêt pour Office 365, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=401408">Configuration requise</a>.</p>
<p>Pour plus d’informations sur la configuration d’Office 365, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=254982">Prise en main d’Office 365</a> et <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Configurer Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Ajouter votre domaine et vérifier la propriété</p></td>
<td><p>Votre domaine est parfois appelé <em>domaine personnel</em> . Vous devez l’ajouter à votre location Office 365, puis effectuez les étapes nécessaires à sa validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine.</p>
<p>Pour ajouter votre domaine à votre location Office 365, suivez les étapes décrites dans l’article <a href="http://go.microsoft.com/fwlink/p/?linkid=254983">Ajouter mon domaine à Office 365</a>.</p>
<p>Effectuez toutes les étapes de chaque section de la rubrique, y compris « Modifier les enregistrements DNS de mes services Office 365 ».</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Vérifier la préparation de votre environnement</p></td>
<td><p>Vous pouvez utiliser l’Assistant de connexion Office 365 pour qu’il vous aide à déployer Office 365. Pour plus dinformations, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=254985">Utiliser l’Assistant Connexion pour déterminer l’état de préparation d’Office 365</a>.</p>
<p>Pour plus d’informations sur l’utilisation de cet outil et sur le déploiement d’Office 365, reportez-vous au <a href="http://go.microsoft.com/fwlink/p/?linkid=257337">Guide de déploiement de Microsoft Office 365</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Préparer la synchronisation Active Directory</p></td>
<td><p>La synchronisation Active Directory permet de synchroniser de manière continue votre annuaire Active Directory local avec Office 365. Cela vous permet de créer des versions synchronisées de chaque groupe et compte d’utilisateur et autorise également la synchronisation de la liste d’adresses globale de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online.</p>

> [!IMPORTANT]  
> Vous devez synchroniser les comptes AD pour tous les utilisateurs Lync dans votre organisation entre vos déploiements locaux et vos déploiements Lync Online, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.

<p>Pour préparer votre environnement en vue de la synchronisation Active Directory, suivez la procédure décrite dans <a href="http://go.microsoft.com/fwlink/p/?linkid=254988">Programme de synchronisation d’annuaire</a>, including setting up single sign-on.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Créer des certificats pour les services de fédération Active Directory (AD FS, Active Directory Federation Services)</p></td>
<td><p>Vous devrez créer les certificats utilisés pour la fédération des identités avec Office 365. Pour plus d’informations, reportez-vous à la section « Certificats de serveur de fédération » de l’article « Planifier et déployer AD FS en vue d’une utilisation avec l’authentification unique » à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Affecter des certificats pour les services AD FS</p></td>
<td><p>Après avoir créé les certificats utilisés pour la fédération des identités avec Office 365, vous devez les installer et les affecter.</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>Déplacer les utilisateurs pilotes vers Skype Entreprise Online</p></td>
<td><p>Après avoir suivi la procédure de préparation et de configuration de votre environnement pour Skype Entreprise Online, vous pouvez commencer à déplacer les utilisateurs pilotes vers Lync Online.</p>
<p>Reportez-vous à <a href="lync-server-2013-move-users-to-lync-online.md">Déplacement des utilisateurs vers Lync Online dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>Administration des utilisateurs dans un déploiement hybride</p></td>
<td><p>Pour plus d’informations sur la façon d’administrer les utilisateurs dans un déploiement hybride, reportez-vous à <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administration des utilisateurs dans un déploiement Lync Server 2013 hybride</a>.</p></td>
</tr>
</tbody>
</table>

