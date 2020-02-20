---
title: Création ou modification d’une collection de paramètres de configuration de réunion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="436b6-102">Création ou modification d’une collection de paramètres de configuration de réunion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436b6-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436b6-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="436b6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="436b6-p101">Les paramètres de la page Configuration de la réunion permettent de définir diverses caractéristiques de l’expérience de participation aux réunions. Par défaut, les paramètres globaux définissent la participation aux réunions. Vous pouvez également créer des paramètres de participation aux réunions au niveau du site et du pool. Si vous créez des paramètres au niveau du pool, ceux-ci s’appliquent à toutes les réunions hébergées par ce pool. Si vous ne créez pas de paramètres au niveau du pool, les paramètres au niveau du site s’appliquent s’ils existent. Si vous ne définissez pas de paramètres au niveau du site, les paramètres globaux s’appliquent à toutes les réunions.</span><span class="sxs-lookup"><span data-stu-id="436b6-p101">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience. By default, the global settings define the join experience. You can also create site-level and pool-level meeting join settings. If you create pool-level settings, those settings apply to all meetings hosted by that pool. If you do not create pool-level settings, site-level settings apply, if they exist. If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="436b6-110">Pour créer des paramètres de participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="436b6-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="436b6-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436b6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436b6-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="436b6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="436b6-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="436b6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="436b6-114">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="436b6-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="436b6-115">Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="436b6-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="436b6-p103">Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="436b6-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="436b6-p104">Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="436b6-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="436b6-p105">Pour acheminer les participants qui appellent depuis le réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants PSTN ignorent la salle d’attente**. Par défaut, les participants qui appellent depuis un réseau RTC accèdent directement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="436b6-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="436b6-124">Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="436b6-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="436b6-125">Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="436b6-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="436b6-p106">Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="436b6-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="436b6-128">Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.</span><span class="sxs-lookup"><span data-stu-id="436b6-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="436b6-p107">Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est automatiquement affecté.</span><span class="sxs-lookup"><span data-stu-id="436b6-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="436b6-p108">Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.</span><span class="sxs-lookup"><span data-stu-id="436b6-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="436b6-133">Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="436b6-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="436b6-134">Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="436b6-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="436b6-135">Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="436b6-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="436b6-136">Si vous n’incluez pas d’URL d’aide personnalisée, l’URL d’aide par défaut de Lync s’affichera dans l’invite.</span><span class="sxs-lookup"><span data-stu-id="436b6-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="436b6-137">Pour personnaliser le logo qui apparaît dans l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo.</span><span class="sxs-lookup"><span data-stu-id="436b6-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="436b6-138">Le logo doit être une image GIF ou JPG d’une taille de 188 par 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="436b6-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="436b6-139">Pour personnaliser le texte d’aide qui apparaît dans l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.</span><span class="sxs-lookup"><span data-stu-id="436b6-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="436b6-140">Pour personnaliser les informations légales qui apparaissent dans l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.</span><span class="sxs-lookup"><span data-stu-id="436b6-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="436b6-141">Pour personnaliser le texte de pied de page qui apparaît dans l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.</span><span class="sxs-lookup"><span data-stu-id="436b6-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="436b6-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="436b6-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="436b6-143">Pour modifier une collection existante de configurations de réunion</span><span class="sxs-lookup"><span data-stu-id="436b6-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="436b6-144">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436b6-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436b6-145">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="436b6-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="436b6-146">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="436b6-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="436b6-147">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="436b6-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="436b6-148">Dans la liste des configurations de réunion, cliquez sur la configuration que vous souhaitez modifier, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="436b6-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="436b6-149">Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="436b6-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="436b6-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="436b6-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="436b6-151">Création de nouveaux paramètres de configuration de réunion à l’aide d’applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="436b6-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="436b6-152">Les paramètres de configuration de réunion peuvent être créés (au niveau de l’étendue du site uniquement) à l’aide de Windows PowerShell et de la cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="436b6-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="436b6-153">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="436b6-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="436b6-154">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="436b6-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="436b6-155">Pour créer des paramètres de configuration de réunion qui utilisent les valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="436b6-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="436b6-156">Cette commande crée un ensemble de paramètres de configuration de réunion pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="436b6-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="436b6-157">Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="436b6-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="436b6-158">Pour modifier une valeur de propriété lors de la création des paramètres de configuration de réunion</span><span class="sxs-lookup"><span data-stu-id="436b6-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="436b6-p112">Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="436b6-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="436b6-161">Pour modifier plusieurs valeurs de propriété lors de la création de paramètres de configuration de réunion</span><span class="sxs-lookup"><span data-stu-id="436b6-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="436b6-p113">Plusieurs valeurs de propriété peuvent être modifiées en incluant plusieurs paramètres. Par exemple, cette commande admet tout le monde à une réunion comme présentateur et force aussi les utilisateurs PSTN à attendre dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :</span><span class="sxs-lookup"><span data-stu-id="436b6-p113">Multiple property values can be modified by including multiple parameters. For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="436b6-164">Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="436b6-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

