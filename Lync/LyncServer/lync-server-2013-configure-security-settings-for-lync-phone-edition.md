---
title: 'Lync Server 2013 : configuration des paramètres de sécurité pour Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fad5a47f8b56bd97386dcab49aef9671c6f99e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="ac411-102">Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac411-102">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac411-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ac411-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ac411-104">Aidez à améliorer la sécurité des appareils exécutant Lync Phone Edition via votre paramètre de sécurité SIP et vos paramètres de verrouillage du téléphone.</span><span class="sxs-lookup"><span data-stu-id="ac411-104">Help improve the security of devices running Lync Phone Edition via your SIP security setting and phone lock settings.</span></span>

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a><span data-ttu-id="ac411-105">Pour configurer les paramètres de sécurité pour Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="ac411-105">To configure security settings for Lync Phone Edition</span></span>

1.  <span data-ttu-id="ac411-106">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ac411-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac411-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ac411-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ac411-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ac411-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ac411-109">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="ac411-109">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

4.  <span data-ttu-id="ac411-110">Sur la page **configuration du périphérique** , dans la liste des configurations des appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ac411-110">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change security settings.</span></span>

5.  <span data-ttu-id="ac411-111">Dans **modifier la configuration**de l’appareil, dans **sécurité SIP**, spécifiez le niveau de sécurité SIP.</span><span class="sxs-lookup"><span data-stu-id="ac411-111">In **Edit Device Configuration**, in **SIP security**, specify the SIP security level.</span></span> <span data-ttu-id="ac411-112">Le niveau par défaut est **élevé**, ce que nous vous recommandons d’utiliser.</span><span class="sxs-lookup"><span data-stu-id="ac411-112">The default level is **High**, which we recommend using.</span></span>

6.  <span data-ttu-id="ac411-113">Dans **modifier la configuration**de l’appareil, sous **verrouillage du téléphone**, activez ou désactivez la case à cocher appliquer le **verrouillage du périphérique** (activée par défaut), spécifiez la longueur minimale du code confidentiel (6 caractères par défaut) et le délai d’expiration (10 minutes par défaut).</span><span class="sxs-lookup"><span data-stu-id="ac411-113">In **Edit Device Configuration**, under **Phone Lock**, select or clear the **Enforce device locking** check box (selected by default) and specify the minimum PIN length (6 characters by default) and timeout period (10 minutes by default).</span></span> <span data-ttu-id="ac411-114">Nous vous recommandons d’utiliser ces valeurs par défaut ou d’augmenter la longueur du code confidentiel et/ou de diminuer le délai d’expiration.</span><span class="sxs-lookup"><span data-stu-id="ac411-114">We recommend using these defaults or increasing the PIN length and/or decreasing the timeout period.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ac411-115">Pour plus d’informations, voir <A href="lync-server-2013-enforce-phone-locking.md">Enforce Phone Locking in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ac411-115">For details, see <A href="lync-server-2013-enforce-phone-locking.md">Enforce phone locking in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ac411-116">Configuration des paramètres de sécurité pour les téléphones Lync Phone Edition à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac411-116">Configuring Security Settings for Lync Phone Edition Phones by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ac411-117">Les paramètres de sécurité peuvent être gérés à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ac411-117">Security settings can be managed by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="ac411-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac411-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ac411-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="ac411-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-modify-the-sip-security-mode"></a><span data-ttu-id="ac411-120">Pour modifier le mode de sécurité SIP</span><span class="sxs-lookup"><span data-stu-id="ac411-120">To modify the SIP security mode</span></span>

  - <span data-ttu-id="ac411-121">Cette commande définit le SIPSecurityMode pour la collection globale des paramètres de téléphone UC sur moyen.</span><span class="sxs-lookup"><span data-stu-id="ac411-121">This command sets the SIPSecurityMode for the global collection of UC phone settings to Medium.</span></span> <span data-ttu-id="ac411-122">La sécurité SIP peut également être définie sur faible ou élevé (valeur par défaut).</span><span class="sxs-lookup"><span data-stu-id="ac411-122">SIP security could also be set to Low or High (the default value).</span></span>
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a><span data-ttu-id="ac411-123">Pour modifier la longueur minimale du code confidentiel</span><span class="sxs-lookup"><span data-stu-id="ac411-123">To modify the minimum PIN length</span></span>

  - <span data-ttu-id="ac411-124">Dans cet exemple, tous les paramètres de téléphone UC sont modifiés pour exiger une longueur de code confidentiel minimale de 7 chiffres.</span><span class="sxs-lookup"><span data-stu-id="ac411-124">In this example, all the UC phone settings are modified to require a minimum PIN length of 7 digits.</span></span>
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

<span data-ttu-id="ac411-125">Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ac411-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ac411-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac411-126">See Also</span></span>


[<span data-ttu-id="ac411-127">Gestion de l’authentification Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac411-127">Managing Lync Server 2013 authentication</span></span>](lync-server-2013-managing-lync-server-authentication.md)  


[<span data-ttu-id="ac411-128">Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac411-128">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

