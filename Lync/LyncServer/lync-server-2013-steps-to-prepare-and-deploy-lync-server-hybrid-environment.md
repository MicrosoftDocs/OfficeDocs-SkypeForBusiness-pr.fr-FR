---
title: 'Lync Server 2013 : étapes de préparation et de déploiement d’un environnement hybride Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7acf5fa315e566094728066bbc798267f029ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519451"
---
# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Étapes de préparation et de déploiement de l’environnement hybride Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

Le tableau suivant répertorie les étapes nécessaires à la préparation de votre environnement pour un déploiement hybride avec Skype entreprise Online et Microsoft Office 365.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Résultat</th>
<th>Étape</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p>Créer un compte client pour Office 365 et activer Lync Online</p></td>
<td><p>Découvrez Office 365 et Lync Online dans <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Pour vous assurer que votre environnement est prêt pour Office 365, reportez-vous à la <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">Configuration système requise</a>.</p>
<p>Pour plus d’informations sur la configuration d’Office 365, voir <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with office 365</a> et <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set up Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Ajouter votre domaine et vérifier la propriété</p></td>
<td><p>Votre domaine est parfois également appelé votre <em>domaine personnel</em>. Vous devez ajouter votre domaine à votre organisation Office 365, puis suivre les étapes de validation du domaine avec Office 365. Cela permet de confirmer que vous êtes le propriétaire du domaine.</p>
<p>Pour ajouter votre domaine à votre organisation Office 365, suivez les étapes décrites dans la rubrique <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">ajouter votre domaine à office 365</a>.</p>
<p>Effectuez toutes les étapes de chaque section de la rubrique, y compris &quot; modifier les enregistrements DNS pour vos services Office 365.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Vérifier la préparation de l’environnement</p></td>
<td><p>Vous pouvez utiliser l’Assistant Installation d’Office 365 pour vous aider à déployer Office 365. Pour plus d’informations, consultez la rubrique <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">utiliser l’Assistant Configuration pour déterminer la préparation d’Office 365</a>.</p>
<p>Pour plus d’informations sur l’utilisation de l’outil et sur le déploiement d’Office 365, voir le <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guide de déploiement d’office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Préparer la synchronisation Active Directory</p></td>
<td><p>La synchronisation Active Directory maintient la synchronisation permanente de votre Active Directory local avec Office 365. Cela vous permet de créer des versions synchronisées de chaque compte d’utilisateur et groupe, et d’activer la synchronisation de la liste d’adresses globale (GAL) à partir de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Vous devez synchroniser les comptes AD de tous les utilisateurs Lync de votre organisation entre vos déploiements Lync sur site et en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et les utilisateurs en ligne de votre organisation peut ne pas fonctionner comme prévu.


</div>
<p>Pour préparer votre environnement à la synchronisation Active Directory, suivez les étapes décrites dans la feuille de <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">route de synchronisation d’annuaires</a>, notamment la configuration de l’authentification unique.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Créer des certificats pour les services ADFS (Active Directory Federation Services)</p></td>
<td><p>Vous devrez créer les certificats qui sont utilisés pour la Fédération des identités avec Office 365. Pour plus d’informations, reportez-vous à la section « certificats de serveur de Fédération » de la rubrique plan for and Deploy AD FS for use with Single Sign-On <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">: Use AD FS pour implémenter et gérer l’authentification unique</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Attribuer des certificats pour AD FS</p></td>
<td><p>Une fois que vous avez créé les certificats qui sont utilisés pour la Fédération des identités avec Office 365, vous devez les installer et les affecter.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Déplacement des utilisateurs pilotes vers Skype entreprise Online</p></td>
<td><p>Une fois que vous avez terminé les étapes de préparation et de configuration de votre environnement pour Skype entreprise Online, vous pouvez commencer à transférer des utilisateurs pilotes vers Lync Online.</p>
<p>Voir <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Administration des utilisateurs dans un déploiement hybride</p></td>
<td><p>Pour plus d’informations sur l’administration des utilisateurs dans un déploiement hybride, voir <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a Hybrid Lync Server 2013 Deployment</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

