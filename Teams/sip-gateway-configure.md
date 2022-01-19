---
title: Configurer la passerelle SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Découvrez comment configurer la passerelle SIP.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1af44c5e3962f89346cae166bf40efa6a8622338
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/18/2022
ms.locfileid: "62065180"
---
# <a name="configure-sip-gateway"></a>Configurer la passerelle SIP

Cet article explique comment configurer la passerelle SIP afin que votre organisation puisse utiliser des appareils SIP compatibles avec Microsoft Teams. Pour savoir ce que la passerelle SIP peut faire pour votre organisation, le matériel, les logiciels et les licences dont votre organisation a besoin pour elle, lisez Planifier la passerelle [SIP.](sip-gateway-plan.md)

Avant de pouvoir configurer la passerelle SIP, vous devez :

- **Rétablissez les paramètres par défaut des appareils SIP.** Vous ou les utilisateurs de votre organisation devez rétablir les paramètres par défaut par défaut de chaque appareil SIP utilisé avec la passerelle SIP. Pour savoir comment faire, consultez les instructions du fabricant.

- **Ouvrez votre pare-feu Microsoft 365 et Teams.** Ouvrez le pare-feu de votre réseau pour Microsoft 365 et Teams trafic informatique, comme décrit dans Office 365 [url et plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- **Assurez-vous que les appareils SIP ne se cachent pas derrière un proxy.** Assurez-vous que le trafic http/s contourne tout proxy http/s d’entreprise.

- **Ouvrez le port UDP.** Ouvrez le port UDP entre 49152 et 53247 pour les plages IP 52.112.0.0/14 à 52.120.0.0/14.

- **Ouvrez le port TCP.** Ouvrez le port TCP 5061 pour les plages IP 52.112.0.0/14 à 52.120.0.0/14.

- **Ouvrez les points de terminaison https suivants (adresses IP et URL) :**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net



Les sections suivantes décrivent ce que vous devez faire en tant qu’administrateur pour configurer la passerelle SIP.

- [Vérifiez que la passerelle SIP est disponible pour votre organisation.](#verify-that-sip-gateway-is-available-for-your-organization)

- [Activez la passerelle SIP pour les utilisateurs de votre organisation.](#enable-sip-gateway-for-the-users-in-your-organization)

- [Définissez l’URL du](#set-the-sip-gateway-provisioning-server-url)serveur de provisionation de passerelle SIP.

Cet article décrit également comment :

- [Inscrivez des appareils SIP individuellement ou par lots selon votre convenance.](#provision-and-enroll-sip-devices-as-common-area-phones)  


- [Affichez et surveillez vos appareils SIP.](#view-and-monitor-sip-devices)

- [Activez la prise en charge d’une interface utilisateur multi language.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Vérifier que la passerelle SIP est disponible pour votre organisation

1. Connectez-vous au [Teams d’administration.](https://admin-teams.microsoft.com/)

2. À gauche, sélectionnez **Teams et** voyez si l’onglet appareils **SIP** est visible. Si c’est le cas, le service passerelle SIP est activé pour votre organisation.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Activer la passerelle SIP pour les utilisateurs de votre organisation

Vous pouvez activer la passerelle SIP pour votre organisation de deux façons : à l’aide du Centre d’administration Teams ou à l’aide d’une cmdlet PowerShell.

### <a name="by-using-teams-admin-center"></a>À l’aide Teams centre d’administration

Pour activer la passerelle SIP dans le Centre Teams’administration, suivez ces étapes :

1. Go to the [Teams admin center](https://admin.teams.microsoft.com/)

2. À gauche, sous **Voix,** sélectionnez **Stratégies d’appel.**

3. À droite sous **Gérer** les stratégies, sélectionnez la stratégie d’appel appropriée attribuée aux utilisateurs ou, si nécessaire, créez une stratégie d’appel et attribuez-la aux utilisateurs requis.

4. Sélectionnez **Gérer les** stratégies, sélectionnez une stratégie, puis sélectionnez **Modifier.**

5. Activer le paramètre pour les **appareils SIP peut être utilisé pour** les appels, puis sélectionnez **Enregistrer.**


### <a name="by-using-powershell"></a>À l’aide de PowerShell

Vous pouvez également activer la passerelle SIP à l’aide de l’cmdlet PowerShell [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) Pour activer les utilisateurs pour les appareils SIP, sélectionnez une stratégie et définissez `-AllowSIPDevicesCalling` l’attribut sur `True` . La valeur par défaut est donc que les utilisateurs ne peuvent pas utiliser leurs appareils SIP, sauf si `False` vous les activez.


> [!NOTE]
> - La propagation des stratégies peut prendre jusqu’à 24 heures.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Définir l’URL du serveur de provisionation de passerelle SIP

Vous pouvez définir l’URL du serveur de configuration de la passerelle SIP dans votre serveur DHCP (Dynamic Host Configuration Protocol). Les utilisateurs qui travaillent à distance doivent le configurer manuellement.

### <a name="using-dhcp"></a>Utilisation de DHCP

Pour chaque appareil SIP, définissez l’une des URL de serveur de provisionnage de passerelle SIP suivantes : 

- EMEA : `http://emea.ipp.sdg.teams.microsoft.com`
- Amériques : `http://noam.ipp.sdg.teams.microsoft.com`
- APAC : `http://apac.ipp.sdg.teams.microsoft.com`

Ajoutez des appareils SIP à votre Teams organisation en configurant l’URL du serveur de configuration de passerelle SIP ci-dessus dans votre serveur DHCP. Pour en savoir plus sur le serveur DHCP, voir [Déployer et gérer DHCP.](/learn/modules/deploy-manage-dynamic-host-configuration-protocol) Vous pouvez également utiliser l’option DHCP 42 pour spécifier le serveur NTP (Network Time Protocol) et l’option DHCP 2 pour spécifier le décalage par rapport au temps universel coordonné (UTC) en secondes. Les appareils de votre organisation seront acheminés vers le serveur de mise en service de la passerelle SIP. Les téléphones SIP correctement mis en service affichent le logo Teams et un bouton soft pour la se connecte.

Assurez-vous que les appareils SIP ont la version de microprogramme minimale prise en charge pour l’intégration. Lors de l’intégration, la passerelle SIP pushe l’interface utilisateur de configuration et d’authentification par défaut sur l’appareil. Pour connaître la version de microprogramme requise pour les appareils SIP, voir [Planifier la passerelle SIP.](sip-gateway-plan.md)

### <a name="manually"></a>Manuellement

Les utilisateurs qui travaillent à distance doivent configurer manuellement l’URL du serveur de configuration sur leur appareil SIP en suivant les étapes suivantes :

1. Ouvrez **Paramètres** sur l’appareil et obtenez l’adresse IP de l’appareil.

2. Ouvrez une fenêtre de navigateur, entrez l’adresse IP de l’appareil, connectez-vous (si nécessaire) et configurez l’URL du serveur de configuration dans l’utilitaire web de l’appareil.

3. Sous **Paramètres** **paramètres avancés ou avancés** sur l’utilitaire web, entrez l’URL du serveur de mise en service indiquée ci-dessus.

> [!NOTE]
> - Seuls les appareils SIP compatibles peuvent être intégrés à la passerelle SIP. 
> - Pour être intégrés, les téléphones CISCO IP doivent être flashés sur le microprogramme à plusieurs plateformes. Pour savoir comment faire, consultez le [guide de conversion du microprogramme de Cisco.](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)
> - Pour les téléphones Yealink, utilisez l’option 66.
> - Pour les téléphones Cisco, Poly et AudioCode, utilisez l’option 160. 
> - Pour les périphériques Cisco, vousPSN.xml **/$** à l’URL du serveur de provisionation.


## <a name="configure-conditional-access"></a>Configurer l’accès conditionnel

L’accès conditionnel est Azure Active Directory (Azure AD) qui permet de s’assurer que les appareils qui accèdent à vos ressources Microsoft 365 sont correctement gérés et sécurisés. La passerelle SIP authentifier les appareils SIP auprès de Azure AD. Ainsi, si votre organisation utilise l’accès conditionnel pour les appareils du réseau d’entreprise, elle doit exclure les adresses IP suivantes :

- Amérique du Nord :
    - Est des États-Unis : 52.170.38.140
    - Ouest des États-Unis : 40.112.144.212
-   Région EMEA :
    - Europe du Nord : 40.112.71.149
    - Europe de l’Ouest : 40.113.112.67
-   Région APAC :
    - Australie Est : 20.92.120.71
    - Australie (Sud-est) : 13.73.115.90

Pour plus d’informations, voir [plages d’adresses IP.](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Provision et inscription des appareils SIP en tant que téléphones de zone commune
> [!NOTE]
> Pour être inscrit, un appareil SIP doit être intégré à la passerelle SIP.

Pour simplifier vos tâches, vous pouvez inscrire des appareils SIP dans le Teams d’administration, un par un ou par lots. Voici comment procéder :

1. Connectez-vous au [**Teams d’administration.**](https://admin.teams.microsoft.com)

2. Sélectionnez **Teams appareils**  >  **SIP sur les appareils mobiles.**

3. En haut à droite, sélectionnez **Périphériques d’approvisionnement d’actions**  >   et suivez l’une des étapes suivantes :

  - **Pour mettre en service un appareil :**

     a. Sous **En attente d’activation,** **sélectionnez Ajouter.**

     b. Dans le **volet Ajouter des adresses MAC,** entrez l’adresse  **MAC** et l’emplacement de l’appareil, puis sélectionnez **Appliquer.**
     
     c. Sous **En attente d’activation,** sélectionnez l’appareil que vous vient d’ajouter, puis **sélectionnez Générer du code de vérification.**
     
     d. Dans le **volet Périphériques** d’approvisionnement, sous Code de **vérification,** notez le code de vérification de l’appareil SIP.

   - **Pour mettre en service plusieurs appareils :**

     a. Sous **En attente d’activation,** à droite, **sélectionnez Exporter** (Microsoft Excel icône).
     
     b. Dans le **volet Provision des appareils,** sous **Télécharger plusieurs adresses MAC,** **sélectionnez Télécharger un modèle.**
     
     c. Enregistrez **Template_Provisioning.csv** sur votre ordinateur et remplissez les champs **ID MAC** **et** Emplacement.
    
     d. Dans le **volet Périphériques** de provision, **sélectionnez Télécharger plusieurs adresses MAC.** 

     e. À droite du Télécharger d’adresses **MAC,** sélectionnez Un **fichier,** puisTemplate_Provisioning.csvfichier contenant vos données. 

     f. Dans le volet **Périphériques** de mise en service, sous En attente **d’activation,** sélectionnez un périphérique, puis sélectionnez Générer du **code** de vérification pour générer un code de vérification à une seule heure pour chaque périphérique mis en service. Notez le code de vérification pour chaque appareil SIP.

4. Sur l’appareil SIP, composez le code de fonctionnalité d’inscription suivi du code de vérification. Sur l’appareil SIP, composez le code de fonctionnalité d’inscription 55* (utilisé par la passerelle SIP pour la validation du code d’inscription unique), suivi du code de vérification généré dans le Centre d’administration Teams pour cet appareil \* particulier. Par exemple, si le code de vérification est 123456, composez \* le 55 \* 123456 pour inscrire l’appareil.

5.  Dans le **volet Provision de périphériques,** sous En attente de **la connectez-vous,** **sélectionnez Connecté.**

6. Dans la **boîte de dialogue Se connectez à** un utilisateur, copiez ou notez le code de coupage de l’appareil SIP.

7. Allez à, puis sous Entrer le code, entrez le code de coupage de [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) l’appareil SIP, puis sélectionnez **Suivant.**

8. Dans la page **de** inscription  à Microsoft, dans le champ Adresse de messagerie ou téléphone, entrez l’adresse de messagerie de l’appareil SIP, puis sélectionnez **Suivant.**

9. Dans la page **Mot** de passe, entrez le mot de passe de l’adresse e-mail de l’appareil SIP, puis **sélectionnez Se connectez.**

10. Sur la **page de la passerelle des appareils SIP** vous essayez de vous Teams, sélectionnez **Continuer.**

## <a name="how-to-sign-in-and-sign-out"></a>Comment se connecter et se signer

Seule l' connect-in locale est prise en charge pour les appareils personnels des utilisateurs. Pour vous sortant d’un appareil à partir du Centre d’administration, suivez ces étapes :

1. Connectez-vous au [**Teams d’administration.**](https://admin.teams.microsoft.com)

2. Sélectionnez **Teams appareils**  >  **SIP sur les appareils mobiles.**

3. Sur la droite, sélectionnez un appareil SIP, puis Se **sortant.**


### <a name="user-pairing-and-sign-in"></a>Coupage et inscription des utilisateurs

Pour coupler un appareil SIP une fois que l’utilisateur s’est authentifié à l’aide des informations d’identification d’entreprise, l’utilisateur doit :

1. Appuyez **sur Se connecter** sur le téléphone SIP pour afficher l’URL d’authentification et le code de coupage. Le code de coupage est sensible à l’heure. S’il expire, l’utilisateur doit appuyer sur Retour sur le téléphone et recommencer le processus de inscription. 

2. Accédez à l’URL d’authentification dans le navigateur mobile ou de bureau de l’utilisateur et utilisez les informations d’identification de l’entreprise pour se connecter.

3. Entrez le code d’appariment affiché sur le téléphone SIP dans l’application d’authentification web pour coupler le téléphone SIP au compte de l’utilisateur. Lors d’une connexion réussie, qui peut prendre un certain temps, le téléphone SIP affiche le numéro de téléphone et le nom d’utilisateur, si l’appareil le prend en charge.

> [!NOTE]
> L’emplacement de l’appareil indiqué sur l’Azure Active Directory d’authentification web est le centre de données de la passerelle SIP auquel l’appareil est connecté. Les téléphones SIP dans l’étendue ne sont pas capables d’utiliser OAuth. Par donc, la passerelle SIP authentifier l’utilisateur via l’application d’authentification web, puis associe l’appareil avec ses informations d’identification. En savoir plus ici : [Plateforme d'identités Microsoft flux d’autorisation d’appareil OAuth 2.0.](/azure/active-directory/develop/v2-oauth2-device-code)

### <a name="sign-out"></a>Se sortant de l’affichage

Pour se sortant, un utilisateur de l’appareil peut :

- Appuyez **sur La sortie sur** l’appareil SIP et suivez les étapes décrites sur l’appareil. 

Pour vous sortant d’un appareil du Centre Teams’administration :

1. Connectez-vous au [**Teams d’administration.**](https://admin.teams.microsoft.com)

2. Sélectionnez **Teams appareils**  >  **SIP sur les appareils mobiles.**

3. À droite, dans le volet des **appareils SIP,** sélectionnez l’appareil.

4. Dans le volet **Détails** de l’appareil, sélectionnez l’onglet **Détails,** puis dans le coin supérieur droit du menu **Actions,** **sélectionnez Se sortant.** 


## <a name="view-and-monitor-sip-devices"></a>Afficher et surveiller des appareils SIP

Vous pouvez afficher et surveiller l’inventaire de vos appareils SIP dans le Centre Teams’administration lorsque les utilisateurs des appareils se connectent au moins une fois. Voici comment procéder :

1. Connectez-vous au [Teams d’administration.](https://admin.teams.microsoft.com/)

2. Sélectionnez **Teams appareils**  >  **SIP sur les appareils mobiles.** Tous les appareils SIP connectés sont répertoriés sur la droite.

## <a name="restart-a-sip-device"></a>Redémarrer un appareil SIP

1. Connectez-vous au [Teams d’administration.](https://admin.teams.microsoft.com)

2. Sélectionnez **Teams appareils**  >  **SIP sur les appareils mobiles.** 

3. À droite, sélectionnez l’appareil SIP que vous voulez redémarrer, puis **redémarrez.**

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Modifications de stratégie de synchronisation apportées aux appareils SIP pour appliquer les stratégies

Les informations et stratégies des utilisateurs seront récupérées sur les appareils SIP lorsque les utilisateurs se connecteront. Les modifications de stratégie qui suivent pour les utilisateurs connectés seront synchronisées avec l’appareil dans l’heure. L’inscription des appareils doit régulièrement être actualisée avec la passerelle SIP. Les téléphones SIP dépendent de la redirection d’appels. L’administrateur doit donc définir `AllowCallRedirect` l’attribut sur `Set-CsTeamsCallingPolicy` `Enabled` .


## <a name="set-a-sip-devices-ui-language"></a>Définir la langue de l’interface utilisateur d’un appareil SIP

Un appareil SIP peut généralement afficher des informations dans de nombreuses langues. La définition de son langage d’interface utilisateur affecte son interface, notamment les touches softkeys et les messages système de sign-in/sign-out. La définition de la langue de l’interface utilisateur s’fait dans le serveur de configuration, à l’aide du serveur DHCP, ou manuellement en a ajouté une chaîne de code dans l’URL comme dans les exemples suivants.

Comment définir l’allemand pour les téléphones Polycom, AudioCodes et Yealink :
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Comment configurer le japonais pour les téléphones Cisco :
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Langues prise en charge

|Nom de la langue|Code de langue]
|-------------|-------------|
|Anglais (par défaut)|fr       |
|Espagnol      |es           |
|Japonais     |ja           |
|Allemand       |de           |
|Français       |fr           |
|Portugais   |pt           |

> [!Note]
> - Le japonais n’est pas pris en charge par Yealink et est partiellement pris en charge par Polycom VVX.
> - Par défaut, le système est l’anglais si la langue sélectionnée n’est pas prise en charge par le point de terminaison SIP.
> - Lorsque le **paramètre lang_xx** n’est pas réglé via l’URL d’approvisionnement, l’anglais est utilisé comme langue par défaut.
> - Si  vous vous connectez pour qu’un texte d’appel d’urgence ne soit pas  traduit dans d’autres langues, une version abrégée en anglais uniquement s’affiche sur Les modèles de téléphone IP suivants pour des raisons de taille d’écran :
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - L’étiquette de touches de messagerie vocale est codée en dur avec du texte **VM** dans toutes les langues pour Poly VVX en raison d’une limitation de longueur de chaîne.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams et IPv6

La passerelle SIP prend en charge uniquement le IPv4. Microsoft Teams prise en charge des services et clients IPv4 et IPv6. Si vous souhaitez contrôler les communications vers Microsoft Teams, utilisez les plages d’adresses IP dans Microsoft 365 url et [plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

## <a name="emergency-calling"></a>Appel d’urgence

La passerelle SIP prend uniquement en charge les adresses de secours statiques (également appelées enregistrées). Actuellement, les adresses enregistrées ne sont pas pris en charge pour les scénarios de routage direct. Pour plus d’informations sur les appels d’urgence, voir [Planifier et gérer les appels d’urgence.](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)

## <a name="report-problems-to-microsoft"></a>Signaler des problèmes à Microsoft

Pour signaler des problèmes, contactez [le Support Microsoft.](https://support.microsoft.com)
