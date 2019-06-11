---
title: 'Lync Server 2013 : Autorisations et conditions prérequises pour la configuration de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-05_

Response Group est une fonctionnalité de gestion des appels voix entreprise. Cette rubrique décrit ce que vous devez mettre en place avant de pouvoir configurer les informations d’identification et les autorisations d’administration dont vous avez besoin pour effectuer des tâches de configuration.

Cette section suppose que vous avez lu la documentation de planification liée au groupe réponse. Pour plus d’informations, reportez-vous à [planification des fonctionnalités de gestion des appels dans Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) dans la documentation de planification.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Outils de configuration et rôles d’administration

Pour configurer Response Group, vous pouvez utiliser les outils d’administration suivants:

  - Panneau de configuration Lync Server

  - outil de configuration Response Group

  - Lync Server Management Shell

Pour configurer les groupes Response Group, vous devez être membre d’au moins l’un des rôles d’administrateur suivants :


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
<td><p>Création d’un flux de travail</p></td>
<td><p>Affectation d’un responsable</p></td>
<td><p>Création/Affectation des agents, des files d’attente</p></td>
<td><p>Création/Gestion des congés et des heures d’ouverture</p></td>
<td><p>Activation/Désactivation d’un flux de travail</p></td>
<td><p>Configuration d’un flux de travail (réponse vocale interactive ou groupe de recherche)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√(2)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
<td><p>√(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
<td><p>√(4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> un objet utilisateur des services de domaine Active Directory doit être membre du groupe de sécurité Active Directory spécifié. Un administrateur ou membre du groupe Active Directory délégué disposant des autorisations appropriées pour ajouter des utilisateurs à un groupe de sécurité (par exemple, administrateur, opérateurs de compte) doit ajouter un objet utilisateur au groupe de sécurité ou au groupe de la liste de contrôle pour l’utilisateur. Utilisez les fonctions indiquées. <STRONG>(2)</STRONG> uniquement pour les flux de travail attribués par le CsResponseGroupAdministrator à CsResponseGroupManager. <STRONG>(3)</STRONG> un responsable de groupe de réponse peut affecter un autre membre de CsResponseGroupManager à un flux de travail géré par le responsable actuel. <STRONG>(4)</STRONG> CsViewOnlyAdministrator ne peut exécuter que des applets de action de type «Get» Lync Server Management Shell.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Conditions préalables à la configuration de Response Group

Response Group nécessite les composants suivants:

  - service d’application

  - application Response Group

  - Modules linguistiques

  - Magasin de fichiers (pour conserver les fichiers audio)

  - Services Web (comprend les outils de configuration de Response Group et la console de connexion et de connexion des agents)

Tous ces composants sont installés par défaut lorsque vous déployez Enterprise Voice.

Vous devrez peut-être effectuer les tâches suivantes avant de configurer Response Group:

  - Activez les utilisateurs pour Lync Server 2013 et voix entreprise.

  - Modification d’un fichier de configuration pour la conformité aux normes FIPS (Federal Information Processing Standard)

  - Modification du classement de base de données pour prendre en charge les caractères Yi, Meng et Zang pour les noms des files d’attente et des groupes d’agents

<div>

## <a name="enabling-users"></a>Activation des utilisateurs

La première étape de la configuration d’un groupe de réponse consiste à créer des groupes d’agents. Avant de créer un groupe d’agents, vous devez activer les utilisateurs qui seront agents pour le groupe de réponses pour Lync Server 2013 et voix entreprise. L’activation des utilisateurs pour Lync Server 2013 est généralement une étape du déploiement du serveur Enterprise Edition Server ou Standard Edition Server. Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, voir [désactiver ou réactiver un compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). L’activation des utilisateurs pour voix entreprise est généralement une étape du déploiement voix entreprise. Pour plus d’informations, reportez-vous à [activer l’application voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Conformité aux normes FIPS

Cette section ne vous concerne que si votre organisation doit se conformer aux normes FIPS (Federal Information Processing Standard).

Pour respecter les normes FIPS, vous devez modifier le fichier d’application Web.config afin d’utiliser un autre algorithme de chiffrement une fois les services web installés. Vous devez préciser qu’ASP.NET utilise l’algorithme de chiffrement triple 3DES (Triple Data Encryption Standard) pour traiter les données d’état d’affichage. Dans le cas d’une application de groupe de réponse, cette exigence s’applique à l’outil de configuration de Response Group et à la console de connexion et de connexion de l’agent. Pour plus d’informations sur cette configuration requise, voir l’article de la base de connaissances Microsoft 911722, «vous pouvez recevoir un message d’erreur lorsque vous accédez à des pages Web ASP.NET dont ViewState est activé après la mise [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)à niveau de ASP.net 1,1 vers ASP.NET 2,0» à l’adresse.

Pour modifier le fichier Web.config, procédez comme suit :

1.  Dans un éditeur de texte, comme Bloc-Notes, ouvrez le fichier d’application Web.config.

2.  Dans le fichier Web. config, recherchez la `<system.web>` section.

3.  Ajoutez la section `<machineKey>` suivante dans la `<system.web>` section:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Enregistrez le fichier Web.config.

5.  Redémarrez le service Internet Information Services (IIS) en exécutant la commande suivante à l’invite de commandes:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Prise en charge des caractères Yi, Meng et Zang

Cette section ne vous concerne que si votre organisation doit prendre en charge les caractères Yi, Meng ou Zang.

<div>


> [!NOTE]  
> Pour plus d’informations sur les caractères Yi, Meng et Zang et pourquoi ils peuvent être importants pour votre déploiement, voir les informations sur les jeux <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>de caractères GB18030.



</div>

Pour assurer une prise en charge des caractères Yi, Meng ou Zang, vous devez modifier le classement de la base de données Rgsconfig. Modifiez le classement de la colonne **Nom** des tableaux ci-dessous dans chaque base de données Rgsconfig :

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Pour SQL Server 2008 R2 et SQL Server 2012, utilisez le classement\_Latin\_général 100 (sensible aux lettres). Si vous utilisez ce classement, certains noms d’objet ne dépendent pas des minuscules/majuscules.

Vous pouvez modifier le classement à l’aide de Microsoft SQL Server Management Studio. Pour plus d’informations sur l’utilisation de cet outil, voir utilisation de [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)SQL Server Management Studio. Pour modifier le classement, procédez comme suit :

1.  Assurez-vous que SQL Server Management Studio est configuré de manière à autoriser les modifications nécessaires à la recréation des tables. Pour plus d’informations, consultez la boîte de dialogue «Enregistrer (non [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186)autorisé)» à l’adresse. Pour plus d’informations sur la définition d’un assemblage de colonnes, voir la section «Procédure: définir l’assemblage de colonnes ( [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)Visual Database Tools)».

2.  À l’aide de Microsoft SQL Server Management Studio, connectez-vous à la base de données Rgsconfig.

3.  Recherchez la table à modifier dans la base de données Rgsconfig, cliquez avec le bouton droit sur la table, puis cliquez sur **Conception**.

4.  Modifiez le classement de la colonne **Nom** et enregistrez la table.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

