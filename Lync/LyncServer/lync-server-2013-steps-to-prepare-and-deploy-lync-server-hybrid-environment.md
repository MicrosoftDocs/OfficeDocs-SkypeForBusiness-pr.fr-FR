---
title: 'Lync Server 2013 : Procédure de préparation et de déploiement d’un environnement hybride Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d239d7a57be1aa96dde1f9ccf30c2965de982017
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a>Procédure de préparation et de déploiement d’un environnement hybride Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-12-08_

Le tableau suivant répertorie les étapes nécessaires pour préparer votre environnement pour un déploiement hybride avec Skype entreprise Online et Microsoft Office 365.


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
<td></td>
<td><p>Créer un compte client pour Office 365 et activer Lync Online</p></td>
<td><p>En savoir plus sur Office 365 et Lync Online dans <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</p>
<p>Pour vérifier que votre environnement est prêt pour Office 365, consultez la <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">Configuration système requise</a>.</p>
<p>Pour plus d’informations sur la configuration d’Office 365, voir <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">mise en route d’office 365</a> et <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Configurer Office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Ajout de votre domaine et vérification de la propriété</p></td>
<td><p>Votre domaine est parfois appelé <em>domaine personnel</em>. Vous devez l’ajouter à votre client Office 365, puis suivre la procédure de validation avec Office 365. Cela permet de confirmer que vous êtes bien le propriétaire du domaine.</p>
<p>Pour ajouter votre domaine à votre client 365 Office, suivez les étapes décrites dans l’article <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">ajouter votre domaine à office 365</a>.</p>
<p>Effectuez toutes les étapes de chaque section de la rubrique, y compris &quot;la modification des enregistrements DNS pour vos services 365 Office.&quot;</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Vérifier la compatibilité de l’environnement</p></td>
<td><p>Vous pouvez utiliser l’Assistant Installation d’Office 365 pour vous aider à déployer Office 365. Pour plus d’informations, reportez-vous <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">à utiliser l’Assistant de configuration pour déterminer la disponibilité d’Office 365</a>.</p>
<p>Pour plus d’informations sur l’utilisation de l’outil et le déploiement d’Office 365, voir le <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guide de déploiement d’office 365</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Préparer la synchronisation Active Directory</p></td>
<td><p>La synchronisation Active Directory maintient votre annuaire Active Directory local synchronisé en continu avec Office 365. Cela vous permet de créer des versions synchronisées de chaque groupe et compte d’utilisateur et de synchroniser la liste d’adresses globale de votre environnement Microsoft Exchange Server local vers Microsoft Exchange Online.</p>
<div>

> [!IMPORTANT]  
> Vous devez synchroniser les comptes d’annonces de tous les utilisateurs de Lync au sein de votre organisation entre votre déploiement local et votre déploiement Lync en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.


</div>
<p>Pour préparer votre environnement en vue de la synchronisation Active Directory, suivez les étapes décrites dans la feuille de route de la <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">synchronisation</a>d’annuaires, y compris la configuration de l’authentification unique.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Créer des certificats pour les services AD FS (Active Directory Federation Services)</p></td>
<td><p>Vous devrez créer les certificats utilisés pour la Fédération des identités avec Office 365. Pour plus d’informations, reportez-vous à la section «certificats de serveur de Fédération» de la rubrique planifier pour le déploiement d’AD FS pour une utilisation avec une connexion unique de la <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">liste de contrôle: utiliser AD FS pour implémenter et gérer l’authentification unique</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Attribuer des certificats pour AD FS</p></td>
<td><p>Après avoir créé les certificats utilisés pour la Fédération des identités avec Office 365, vous devez les installer et les affecter.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Déplacer les utilisateurs pilotes vers Skype entreprise Online</p></td>
<td><p>Après avoir suivi les étapes de préparation et de configuration de votre environnement pour Skype entreprise Online, vous pouvez commencer à déplacer les utilisateurs pilotes vers Lync Online.</p>
<p>Voir <a href="lync-server-2013-move-users-to-lync-online.md">déplacer des utilisateurs vers Lync Online dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Administration des utilisateurs dans un déploiement hybride</p></td>
<td><p>Pour plus d’informations sur la façon d’administrer les utilisateurs dans un déploiement hybride, consultez <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administration des utilisateurs dans un déploiement 2013 hybride de Lync Server</a>.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

