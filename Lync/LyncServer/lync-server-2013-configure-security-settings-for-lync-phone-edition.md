---
title: 'Lync Server 2013 : configurer les paramètres de sécurité pour Lync Phone Edition'
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
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Configurer les paramètres de sécurité de Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Aidez-vous à améliorer la sécurité des appareils exécutant Lync Phone Edition via le paramètre de sécurité SIP et les paramètres de verrouillage du téléphone.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Pour configurer les paramètres de sécurité de Lync Phone Edition

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur Configuration de l' **appareil**.

4.  Dans la page Configuration de l' **appareil** , dans la liste des configurations d’appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de sécurité.

5.  Dans **modifier la configuration**de l’appareil, dans **sécurité SIP**, spécifiez le niveau de sécurité SIP. Le niveau par défaut est **élevé**, que nous vous recommandons d’utiliser.

6.  Dans **modifier la configuration**de l’appareil, sous **verrouillage du téléphone**, activez ou désactivez la case à cocher appliquer le verrouillage de l' **appareil** (option activée par défaut), puis spécifiez la longueur minimale du code confidentiel (6 caractères par défaut) et le délai d’expiration (10 minutes par défaut). Nous vous recommandons d’utiliser ces valeurs par défaut ou d’augmenter la longueur du code confidentiel et/ou de réduire le délai d’expiration.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations, voir <A href="lync-server-2013-enforce-phone-locking.md">renforcer le verrouillage du téléphone dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Configuration des paramètres de sécurité des téléphones Lync Phone Edition à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez gérer les paramètres de sécurité à l’aide de Lync Server Management Shell et de l’applet **de passe Get-CsUCPhoneConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-modify-the-sip-security-mode"></a>Pour modifier le mode de sécurité SIP

  - Cette commande définit l’SIPSecurityMode pour la collection globale de paramètres du téléphone monouc sur moyenne. La sécurité SIP peut également être définie sur faible ou haut (valeur par défaut).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Pour modifier la longueur minimale du code confidentiel

  - Dans cet exemple, tous les paramètres de téléphone monouc sont modifiés pour exiger une longueur minimale de 7 chiffres pour le code confidentiel.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

