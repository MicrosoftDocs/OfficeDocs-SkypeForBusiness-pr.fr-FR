---
title: 'Lync Server 2013 : configuration des États de présence personnalisés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526991"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="3390b-102">Configuration des États de présence personnalisés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3390b-102">Configuring custom presence states in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3390b-103">_**Dernière modification de la rubrique :** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="3390b-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="3390b-104">Pour définir des États de présence personnalisés dans Lync 2013, créez un fichier de configuration de présence personnalisée XML, puis spécifiez son emplacement à l’aide des cmdlets Lync Server Management Shell **New-CSClientPolicy** ou **Set-CSClientPolicy** avec le paramètre CustomStateURL.</span><span class="sxs-lookup"><span data-stu-id="3390b-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="3390b-105">Les fichiers de configuration ont les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="3390b-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="3390b-106">Les États de présence personnalisés peuvent être configurés avec les indicateurs de présence disponible, occupé et ne pas déranger.</span><span class="sxs-lookup"><span data-stu-id="3390b-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="3390b-107">L’attribut Availability détermine l’indicateur de présence associé au texte d’état de l’état personnalisé.</span><span class="sxs-lookup"><span data-stu-id="3390b-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="3390b-108">Dans l’exemple plus loin dans cette rubrique, le texte d’État travail à partir de la maison est affiché à droite de l’indicateur de présence vert (disponible).</span><span class="sxs-lookup"><span data-stu-id="3390b-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="3390b-109">La longueur maximale du texte d’État est de 64 caractères.</span><span class="sxs-lookup"><span data-stu-id="3390b-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="3390b-110">Il est possible d’ajouter un maximum de quatre États de présence personnalisés.</span><span class="sxs-lookup"><span data-stu-id="3390b-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="3390b-111">Le paramètre CustomStateURL spécifie l’emplacement du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="3390b-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="3390b-112">Dans Lync 2013, le mode de sécurité élevée SIP est activé par défaut, vous devrez donc stocker le fichier de configuration de présence personnalisé sur un serveur Web sur lequel le protocole HTTPs est activé.</span><span class="sxs-lookup"><span data-stu-id="3390b-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="3390b-113">Dans le cas contraire, les clients Lync 2013 ne pourront pas s’y connecter.</span><span class="sxs-lookup"><span data-stu-id="3390b-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="3390b-114">Par exemple, une adresse valide serait `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` .</span><span class="sxs-lookup"><span data-stu-id="3390b-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3390b-115">Bien qu’elle ne soit pas recommandée dans un environnement de production, vous pouvez tester un fichier de configuration qui se trouve sur un partage de fichiers non HTTPs à l’aide du paramètre de Registre EnableSIPHighSecurityMode pour désactiver le mode haute sécurité SIP sur le client.</span><span class="sxs-lookup"><span data-stu-id="3390b-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="3390b-116">Vous pouvez ensuite utiliser le paramètre de Registre CustomStateURL pour spécifier un emplacement autres que HTTPs pour le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="3390b-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="3390b-117">Notez que Lync 2013 honore les paramètres de Registre Lync 2010, mais que la ruche de registre a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="3390b-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="3390b-118">Vous devez créer les paramètres de Registre comme suit :</span><span class="sxs-lookup"><span data-stu-id="3390b-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3390b-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="3390b-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="3390b-120">Type : DWORD</span><span class="sxs-lookup"><span data-stu-id="3390b-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="3390b-121">Données de la valeur : 0</span><span class="sxs-lookup"><span data-stu-id="3390b-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="3390b-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="3390b-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="3390b-123">Type : String (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="3390b-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="3390b-124">Données de la valeur (exemples) : file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="3390b-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="3390b-125">Localisez votre état de présence personnalisé en spécifiant un ou plusieurs schémas d’ID de paramètres régionaux (LCID) dans le fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="3390b-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="3390b-126">L’exemple ci-dessous montre la localisation en anglais-États-Unis (1033), Norvégien-Bokmål (1044), français-France (1036) et turc (1055).</span><span class="sxs-lookup"><span data-stu-id="3390b-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="3390b-127">Pour obtenir la liste des LCID, consultez la rubrique paramètres régionaux attribués par Microsoft à l’adresse <https://go.microsoft.com/fwlink/p/?linkid=157331> .</span><span class="sxs-lookup"><span data-stu-id="3390b-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="3390b-128">Pour ajouter des États de présence personnalisés à Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3390b-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="3390b-129">Créez un fichier de configuration XML qui utilise le format de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="3390b-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="3390b-130">Enregistrez le fichier de configuration XML sur un serveur Web avec le protocole HTTPs activé.</span><span class="sxs-lookup"><span data-stu-id="3390b-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="3390b-131">Dans cet exemple, le fichier est nommé Presence.xml et enregistré à l’emplacement https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml .</span><span class="sxs-lookup"><span data-stu-id="3390b-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="3390b-132">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3390b-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="3390b-133">Dans Lync Server Management Shell, définissez l’emplacement de votre fichier de configuration XML à l’aide d’une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="3390b-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="3390b-134">Utilisez l’applet de commande **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3390b-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="3390b-135">Pour plus d’informations, voir [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) dans la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3390b-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="3390b-136">Par défaut, Lync Server 2013 &nbsp; met à jour les stratégies et les paramètres du client toutes les trois heures.</span><span class="sxs-lookup"><span data-stu-id="3390b-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="3390b-137">Si vous souhaitez continuer à utiliser les paramètres de stratégie de groupe des versions précédentes, comme CustomStateURL, Lync 2013 reconnaît les paramètres s’ils se trouvent dans la nouvelle ruche de registre de stratégie (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="3390b-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="3390b-138">Toutefois, les stratégies de client basées sur un serveur sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="3390b-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

