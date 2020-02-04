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
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="9ad6a-102">Configuration des États de présence personnalisés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ad6a-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ad6a-103">_**Dernière modification de la rubrique :** 2013-01-10_</span><span class="sxs-lookup"><span data-stu-id="9ad6a-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="9ad6a-104">Pour définir des États de présence personnalisés dans Lync 2013, créez un fichier de configuration de présence XML personnalisé, puis spécifiez son emplacement à l’aide des applets de technologie Lync Server Management Shell **New-CSClientPolicy** ou **Set-CSClientPolicy** avec le paramètre CustomStateURL.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="9ad6a-105">Les fichiers de configuration sont dotés des propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="9ad6a-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="9ad6a-106">Les statuts de présence personnalisés peuvent être configurés avec les indicateurs de présence disponible, occupé et ne pas déranger.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="9ad6a-107">L’attribut Availability détermine quel indicateur de présence est associé au texte d’état de l’état personnalisé.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="9ad6a-108">Dans l’exemple ci-dessous, le texte d’État qui travaille à partir de l’accueil est affiché à droite de l’indicateur de présence vert (disponible).</span><span class="sxs-lookup"><span data-stu-id="9ad6a-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="9ad6a-109">La longueur maximale du texte de statut est de 64 caractères.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="9ad6a-110">Vous pouvez ajouter un maximum de quatre États de présence personnalisés.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="9ad6a-111">Le paramètre CustomStateURL spécifie l’emplacement du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="9ad6a-112">Dans Lync 2013, le mode haute sécurité SIP est activé par défaut, de sorte que vous devrez stocker le fichier de configuration de présence personnalisée sur un serveur Web sur lequel HTTPs est activé.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="9ad6a-113">Dans le cas contraire, les clients 2013 Lync ne seront pas en mesure de s’y connecter.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="9ad6a-114">Par exemple, une adresse valide est `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ad6a-115">Même si cette option n’est pas recommandée dans un environnement de production, vous pouvez tester un fichier de configuration situé sur un partage de fichiers non HTTPs à l’aide du paramètre de Registre EnableSIPHighSecurityMode pour désactiver le mode haute sécurité SIP sur le client.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="9ad6a-116">Vous pouvez ensuite utiliser le paramètre de Registre CustomStateURL pour spécifier un emplacement non HTTP pour le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="9ad6a-117">Notez que Lync 2013 respecte les paramètres de registre de Lync 2010, mais la ruche du registre a été mise à jour.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="9ad6a-118">Vous pouvez créer les paramètres de Registre comme suit :</span><span class="sxs-lookup"><span data-stu-id="9ad6a-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="9ad6a-119">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="9ad6a-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="9ad6a-120">Type : DWORD</span><span class="sxs-lookup"><span data-stu-id="9ad6a-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="9ad6a-121">Données de la valeur : 0</span><span class="sxs-lookup"><span data-stu-id="9ad6a-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="9ad6a-122">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="9ad6a-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="9ad6a-123">Tapez chaîne (REG_SZ).</span><span class="sxs-lookup"><span data-stu-id="9ad6a-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="9ad6a-124">Données de la valeur (exemples)\\: file://lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.Xml</span><span class="sxs-lookup"><span data-stu-id="9ad6a-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="9ad6a-125">Localisez votre état de présence personnalisé en spécifiant un ou plusieurs schémas d’ID de paramètres régionaux (LCID) dans le fichier de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="9ad6a-126">L’exemple plus loin dans cette rubrique montre la localisation en anglais-États-Unis (1033), Norvégien-Bokmål (1044), français-France (1036) et turc (1055).</span><span class="sxs-lookup"><span data-stu-id="9ad6a-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="9ad6a-127">Pour obtenir une liste de LCID, voir ID de paramètres régionaux attribués <http://go.microsoft.com/fwlink/p/?linkid=157331>par Microsoft à.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <http://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="9ad6a-128">Pour ajouter des États de présence personnalisés à Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9ad6a-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="9ad6a-129">Créez un fichier de configuration XML qui utilise le format de l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="9ad6a-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
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

2.  <span data-ttu-id="9ad6a-130">Enregistrez le fichier de configuration XML sur un serveur Web avec HTTPs activé.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="9ad6a-131">Dans cet exemple, le fichier est nommé Presence. xml et enregistré à l’emplacement https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="9ad6a-132">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9ad6a-133">Dans Lync Server Management Shell, définissez l’emplacement de votre fichier de configuration XML à l’aide d’une commande similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="9ad6a-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="9ad6a-134">Utilisez l’applet de passe **Grant-CSClientPolicy** pour affecter cette nouvelle stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="9ad6a-135">Pour plus d’informations, reportez-vous à [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) dans la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="9ad6a-136">Par défaut, la mise à&nbsp;jour des stratégies client et des paramètres de Lync Server 2013 toutes les trois heures.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="9ad6a-137">Si vous voulez continuer à utiliser les paramètres de stratégie de groupe des versions précédentes, telles que CustomStateURL, Lync 2013 reconnaîtra les paramètres s’ils se trouvent dans la nouvelle ruche du registre de la stratégie (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span><span class="sxs-lookup"><span data-stu-id="9ad6a-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="9ad6a-138">En revanche, les stratégies de client serveur sont prioritaires.</span><span class="sxs-lookup"><span data-stu-id="9ad6a-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

