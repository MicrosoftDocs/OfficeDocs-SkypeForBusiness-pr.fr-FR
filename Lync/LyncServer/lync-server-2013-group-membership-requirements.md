---
title: 'Lync Server 2013 : conditions requises d’appartenance au groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="dc304-102">Configuration requise pour l’appartenance à un groupe pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc304-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc304-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="dc304-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="dc304-104">Le tableau suivant résume le ou les groupes auxquels une personne doit appartenir afin d’installer, de gérer et de dépanner Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc304-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc304-105">Exécutable Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc304-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="dc304-106">Appartenance au groupe requis</span><span class="sxs-lookup"><span data-stu-id="dc304-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc304-107"><strong>Setup. exe</strong> – exécutable qui démarre l’installation des outils d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc304-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="dc304-108">Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté.</span><span class="sxs-lookup"><span data-stu-id="dc304-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="dc304-109">Membre du groupe utilisateurs du domaine pour lire les informations dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc304-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="dc304-110">Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).</span><span class="sxs-lookup"><span data-stu-id="dc304-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="dc304-111">Vous pouvez également déléguer des autorisations de configuration aux utilisateurs ou groupes auxquels vous ne voulez pas accorder d’appartenance au groupe Administrateurs de domaine.</span><span class="sxs-lookup"><span data-stu-id="dc304-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="dc304-112">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="dc304-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc304-113"><strong>Deploy.exe</strong> : appelé par setup.exe, deploy.exe est chargé du déploiement des composants logiciels pour les rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="dc304-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="dc304-114">Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté.</span><span class="sxs-lookup"><span data-stu-id="dc304-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="dc304-115">Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="dc304-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="dc304-116">Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).</span><span class="sxs-lookup"><span data-stu-id="dc304-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="dc304-117">L’appartenance au groupe RtcUniversalReadOnlyAdmins est nécessaire pour lire le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="dc304-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="dc304-118">Si vous exécutez le système d’exploitation Windows Vista ou Windows 7, vous serez invité par le contrôle de compte d’utilisateur pour poursuivre l’installation.</span><span class="sxs-lookup"><span data-stu-id="dc304-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="dc304-119">Si vous avez ouvert la session avec un compte d’utilisateur standard, vous devrez demander à une personne membre du groupe Administrateurs local de vous fournir les informations d’identification requises qui vous seront demandées pour installer le logiciel avec le compte approprié.</span><span class="sxs-lookup"><span data-stu-id="dc304-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc304-120"><strong>Bootstrapper.exe</strong> : appelé par setup.exe, bootstrapper.exe est responsable du déploiement et de la configuration des rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="dc304-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="dc304-p105">Membre du groupe Administrateurs local sur l’ordinateur sur lequel le fichier exécutable est exécuté. Membre du groupe RTCUniversalServerAdmins pour exécuter Bootstrapper.exe. Membre du groupe Utilisateurs du domaine pour lire les informations des services de domaine Active Directory (AD DS). Ce niveau d’autorisation est obligatoire puisque l’installation automatique des packages MSI requis sur l’ordinateur local exige des privilèges permettant d’accéder en lecture et en écriture aux ressources protégées des ordinateurs locaux, notamment les répertoires Program Files et les éléments de Registre protégés, telles que la ruche Local Machine (ordinateur local).
</span><span class="sxs-lookup"><span data-stu-id="dc304-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc304-125"><strong>TopologyBuilder</strong> – interface utilisateur basée sur l’Assistant pour créer, afficher, ajuster et valider des topologies Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc304-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="dc304-126">Membre du groupe Administrateurs local sur l’ordinateur à partir duquel le fichier exécutable est exécuté pour examiner la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc304-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="dc304-127">Membre du groupe RTCUniversalServerAdmins pour modifier les paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="dc304-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="dc304-128">Membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs de domaine ou membre du groupe RTCUniversalServerAdmins (uniquement si le groupe s’est vu accorder des autorisations de configuration déléguées) pour publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="dc304-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="dc304-129">Pour plus d’informations sur la délégation d’autorisations de configuration pour permettre aux membres du groupe RTCUniversalServerAdmins de publier la topologie sans être membres du groupe administrateurs du domaine, consultez la rubrique <a href="lync-server-2013-granting-setup-permissions.md">octroi d’autorisations de configuration dans Lync Server 2013</a> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="dc304-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc304-130"><strong>AdminUIHost</strong> : interface utilisateur Web basée sur le Web pour la gestion de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc304-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dc304-131">Membre du groupe CsAdministrator ou membre d’un autre rôle RBAC (contrôle d’accès basé sur un rôle) auquel la tâche d’administration spécifique est affectée.</span><span class="sxs-lookup"><span data-stu-id="dc304-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="dc304-132">Le panneau de configuration Lync Server 2013 implémente les modifications de configuration en exécutant les applets de commande de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc304-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="dc304-133">Pour obtenir la liste des rôles prédéfinis et les membres des cmdlets autorisés à s’exécuter, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="dc304-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc304-134"><strong>PowerShell. exe avec le module Lync Server 2013 chargé</strong> – outil d’administration de ligne de commande avec cmdlets spécifique à la gestion de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc304-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dc304-135">Membre du groupe CsAdministrator ou d’un autre rôle RBAC auquel l’applet de commande spécifique a été affectée.</span><span class="sxs-lookup"><span data-stu-id="dc304-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="dc304-136">Pour obtenir la liste des rôles prédéfinis et les membres des cmdlets autorisés à s’exécuter, voir <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="dc304-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="dc304-137">Ou bien, membre d’un ou plusieurs des groupes suivants, en fonction de l’applet de commande :</span><span class="sxs-lookup"><span data-stu-id="dc304-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc304-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dc304-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="dc304-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="dc304-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="dc304-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="dc304-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

