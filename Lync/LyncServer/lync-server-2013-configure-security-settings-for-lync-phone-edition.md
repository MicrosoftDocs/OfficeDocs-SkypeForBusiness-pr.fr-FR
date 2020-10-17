---
title: 'Lync Server 2013 : configuration des paramètres de sécurité pour Lync Phone Edition'
description: 'Lync Server 2013 : configurez les paramètres de sécurité pour Lync Phone Edition.'
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
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564350"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Aidez à améliorer la sécurité des appareils exécutant Lync Phone Edition via votre paramètre de sécurité SIP et vos paramètres de verrouillage du téléphone.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Pour configurer les paramètres de sécurité pour Lync Phone Edition

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration du périphérique**.

4.  Sur la page **configuration du périphérique** , dans la liste des configurations des appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de sécurité.

5.  Dans **modifier la configuration**de l’appareil, dans **sécurité SIP**, spécifiez le niveau de sécurité SIP. Le niveau par défaut est **élevé**, ce que nous vous recommandons d’utiliser.

6.  Dans **modifier la configuration**de l’appareil, sous **verrouillage du téléphone**, activez ou désactivez la case à cocher appliquer le **verrouillage du périphérique** (activée par défaut), spécifiez la longueur minimale du code confidentiel (6 caractères par défaut) et le délai d’expiration (10 minutes par défaut). Nous vous recommandons d’utiliser ces valeurs par défaut ou d’augmenter la longueur du code confidentiel et/ou de diminuer le délai d’expiration.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations, voir <A href="lync-server-2013-enforce-phone-locking.md">Enforce Phone Locking in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Configuration des paramètres de sécurité pour les téléphones Lync Phone Edition à l’aide des applets de commande Windows PowerShell

Les paramètres de sécurité peuvent être gérés à l’aide de Lync Server Management Shell et de la cmdlet **Get-CsUCPhoneConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-modify-the-sip-security-mode"></a>Pour modifier le mode de sécurité SIP

  - Cette commande définit le SIPSecurityMode pour la collection globale des paramètres de téléphone UC sur moyen. La sécurité SIP peut également être définie sur faible ou élevé (valeur par défaut).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>Pour modifier la longueur minimale du code confidentiel

  - Dans cet exemple, tous les paramètres de téléphone UC sont modifiés pour exiger une longueur de code confidentiel minimale de 7 chiffres.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Pour plus d’informations, consultez la rubrique [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

