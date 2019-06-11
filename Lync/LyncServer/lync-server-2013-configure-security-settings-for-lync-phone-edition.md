---
title: 'Lync Server 2013: configurer les paramètres de sécurité pour Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="2d85f-102">Configurer les paramètres de sécurité de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d85f-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d85f-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2d85f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2d85f-104">Aidez-vous à améliorer la sécurité des appareils exécutant Lync Phone Edition via le paramètre de sécurité SIP et les paramètres de verrouillage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="2d85f-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="2d85f-105">Pour configurer les paramètres de sécurité de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2d85f-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="2d85f-106">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="2d85f-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d85f-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d85f-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d85f-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d85f-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d85f-109">Dans la barre de navigation gauche, cliquez sur **clients**, puis sur Configuration de l' **appareil**.</span><span class="sxs-lookup"><span data-stu-id="2d85f-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="2d85f-110">Dans la page Configuration de l' **appareil** , dans la liste des configurations d’appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de sécurité.</span><span class="sxs-lookup"><span data-stu-id="2d85f-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="2d85f-111">Dans **modifier la configuration**de l’appareil, dans **sécurité SIP**, spécifiez le niveau de sécurité SIP.</span><span class="sxs-lookup"><span data-stu-id="2d85f-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="2d85f-112">Le niveau par défaut est **élevé**, que nous vous recommandons d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="2d85f-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="2d85f-113">Dans **modifier la configuration**de l’appareil, sous **verrouillage du téléphone**, activez ou désactivez la case à cocher appliquer le verrouillage de l' **appareil** (option activée par défaut), puis spécifiez la longueur minimale du code confidentiel (6 caractères par défaut) et le délai d’expiration (10 minutes par défaut).</span><span class="sxs-lookup"><span data-stu-id="2d85f-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="2d85f-114">Nous vous recommandons d’utiliser ces valeurs par défaut ou d’augmenter la longueur du code confidentiel et/ou de réduire le délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="2d85f-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d85f-115">Pour plus d’informations, voir <A href="lync-server-2013-enforce-phone-locking.md">renforcer le verrouillage du téléphone dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2d85f-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d85f-116">Configuration des paramètres de sécurité des téléphones Lync Phone Edition à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d85f-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2d85f-117">Vous pouvez gérer les paramètres de sécurité à l’aide de Lync Server Management Shell et de l’applet **de passe Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2d85f-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="2d85f-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d85f-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2d85f-119">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="2d85f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="2d85f-120">Pour modifier le mode de sécurité SIP</span><span class="sxs-lookup"><span data-stu-id="2d85f-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="2d85f-121">Cette commande définit l’SIPSecurityMode pour la collection globale de paramètres du téléphone monouc sur moyenne.</span><span class="sxs-lookup"><span data-stu-id="2d85f-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="2d85f-122">La sécurité SIP peut également être définie sur faible ou haut (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="2d85f-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="2d85f-123">Pour modifier la longueur minimale du code confidentiel</span><span class="sxs-lookup"><span data-stu-id="2d85f-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="2d85f-124">Dans cet exemple, tous les paramètres de téléphone monouc sont modifiés pour exiger une longueur minimale de 7 chiffres pour le code confidentiel.</span><span class="sxs-lookup"><span data-stu-id="2d85f-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="2d85f-125">Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="2d85f-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d85f-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2d85f-126">See Also</span></span>


[<span data-ttu-id="2d85f-127">Gestion de l’authentification Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d85f-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="2d85f-128">Gestion des appareils, des téléphones et des applications client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d85f-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

