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
ms.openlocfilehash: d33573d86f2bcb485f6a7e7cfc550ea1f3184223
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270489"
---
# <a name="configure-sip-gateway"></a>Configurer la passerelle SIP

Cet article explique comment configurer la passerelle SIP afin que votre organisation puisse utiliser des appareils SIP compatibles avec Microsoft Teams. Pour savoir ce que la passerelle SIP peut faire pour votre organisation et le matériel, les logiciels et les licences dont votre organisation a besoin pour celle-ci, lisez [Plan for SIP Gateway](sip-gateway-plan.md).

Avant de pouvoir configurer la passerelle SIP, procédez comme suit :

- **Réinitialiser les appareils SIP aux paramètres d’usine par défaut.** Vous ou les utilisateurs de votre organisation devez réinitialiser les paramètres par défaut de chaque appareil SIP utilisé avec la passerelle SIP. Pour savoir comment procéder, consultez les instructions du fabricant.

- **Ouvrez votre pare-feu sur Microsoft 365 et Teams.** Ouvrez le pare-feu de votre réseau pour le trafic Microsoft 365 et Teams, comme décrit dans [Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Les règles de pare-feu sont nécessaires uniquement pour le trafic sortant.

- **Assurez-vous que les appareils SIP ne se trouvent pas derrière un proxy.** Assurez-vous que le trafic http/s contourne n’importe quel proxy http/s d’entreprise.

- **Ouvrez le port UDP.** Ouvrez le port UDP dans la plage 49152 à 53247 pour les plages IP 52.112.0.0/14 et 52.120.0.0/14.

- **Ouvrez le port TCP.** Ouvrez le port TCP 5061 pour les plages IP 52.112.0.0/14 et 52.120.0.0/14.

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

- [Vérifiez que la passerelle SIP est disponible pour votre organisation](#verify-that-sip-gateway-is-available-for-your-organization).

- [Activez la passerelle SIP pour les utilisateurs de votre organisation](#enable-sip-gateway-for-the-users-in-your-organization).

- [Définissez l’URL du serveur d’approvisionnement de la passerelle SIP](#set-the-sip-gateway-provisioning-server-url).

Cet article explique également comment :

- [Inscrivez des appareils SIP individuellement ou par lots pour votre commodité](#provision-and-enroll-sip-devices-as-common-area-phones).  

- [Affichez et surveillez vos appareils SIP.](#view-and-monitor-sip-devices)

- [Activez la prise en charge d’une interface utilisateur multilingue.](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>Vérifier que la passerelle SIP est disponible pour votre organisation

1. Connectez-vous au [Centre d’administration Teams](https://admin.teams.microsoft.com/).

2. À gauche, sélectionnez **Appareils Teams** et vérifiez si l’onglet **Appareils SIP** est visible. Si c’est le cas, le service de passerelle SIP est activé pour votre organisation.

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>Activer la passerelle SIP pour les utilisateurs de votre organisation

Vous pouvez activer la passerelle SIP pour votre organisation de deux manières : à l’aide du Centre d’administration Teams ou d’une applet de commande PowerShell.

### <a name="by-using-teams-admin-center"></a>À l’aide du Centre d’administration Teams

Pour activer la passerelle SIP dans le Centre d’administration Teams, procédez comme suit :

1. Accéder au [Centre d’administration Teams](https://admin.teams.microsoft.com/)

2. À gauche, sous **Voix**, **sélectionnez Stratégies d’appel**.

3. À droite sous **Gérer les stratégies**, sélectionnez la stratégie d’appel appropriée affectée aux utilisateurs ou, si nécessaire, créez une stratégie d’appel et attribuez-la aux utilisateurs requis.

4. Sélectionnez **Gérer les stratégies**, sélectionnez une stratégie, puis **sélectionnez Modifier**.

5. Activez le paramètre pour **les appareils SIP qui peuvent être utilisés pour les appels**, puis **sélectionnez Enregistrer**.


### <a name="by-using-powershell"></a>À l’aide de PowerShell

Vous pouvez également activer la passerelle SIP à l’aide de l’applet de commande PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) . Pour activer les utilisateurs pour les appareils SIP, sélectionnez une stratégie et définissez l’attribut `-AllowSIPDevicesCalling` `True`sur . La valeur par défaut étant `False`, les utilisateurs ne pourront pas utiliser leurs appareils SIP, sauf si vous les activez.

> [!NOTE]
> - La propagation de stratégie peut prendre jusqu’à 24 heures.

## <a name="set-the-sip-gateway-provisioning-server-url"></a>Définir l’URL du serveur d’approvisionnement de passerelle SIP

Vous pouvez définir l’URL du serveur d’approvisionnement de la passerelle SIP dans votre serveur DHCP (Dynamic Host Configuration Protocol). Les utilisateurs qui travaillent à distance doivent le configurer manuellement.

### <a name="using-dhcp"></a>Utilisation de DHCP

Pour chaque appareil SIP, définissez l’une des URL de serveur d’approvisionnement de passerelle SIP suivantes : 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- Amériques: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

Ajoutez des appareils SIP à votre organisation Teams en configurant l’URL du serveur d’approvisionnement de passerelle SIP ci-dessus dans votre serveur DHCP. Pour en savoir plus sur le serveur DHCP, consultez [Déployer et gérer DHCP](/learn/modules/deploy-manage-dynamic-host-configuration-protocol). En outre, vous pouvez utiliser l’option DHCP 42 pour spécifier le serveur NTP (Network Time Protocol) et l’option DHCP 2 pour spécifier le décalage du temps universel coordonné (UTC) en secondes. Les appareils de votre organisation seront routées vers le serveur d’approvisionnement de la passerelle SIP. Les téléphones SIP correctement approvisionnés affichent le logo Teams et un bouton soft pour la connexion.

Vérifiez que les appareils SIP sont sur la version minimale du microprogramme prise en charge pour l’intégration. Lors de l’intégration, la passerelle SIP envoie (push) l’interface utilisateur de configuration et d’authentification par défaut à l’appareil. Pour connaître la version requise du microprogramme pour les appareils SIP, consultez [Plan for SIP Gateway](sip-gateway-plan.md).

### <a name="manually"></a>Manuellement

Les utilisateurs qui travaillent à distance doivent configurer manuellement l’URL du serveur d’approvisionnement dans leur appareil SIP en procédant comme suit :

1. Ouvrez **Paramètres** sur l’appareil et obtenez l’adresse IP de l’appareil.

2. Ouvrez une fenêtre de navigateur, entrez l’adresse IP de l’appareil, connectez-vous (si nécessaire) et configurez l’URL du serveur d’approvisionnement dans l’utilitaire web de l’appareil.

3. Sous **Paramètres** ou **Paramètres avancés** sur l’utilitaire web, entrez l’URL du serveur d’approvisionnement indiquée ci-dessus.

> [!NOTE]
> - Seuls les appareils SIP compatibles peuvent être intégrés à la passerelle SIP. 
> - Les téléphones IP Cisco doivent être flashés sur le microprogramme multiplateforme avant de pouvoir être intégrés. Pour savoir comment faire, consultez le [guide de conversion du microprogramme Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html).
> - Pour les téléphones Yealink, utilisez l’option 66.
> - Pour les téléphones Cisco, Poly et AudioCode, utilisez l’option 160. 
> - Pour les appareils Cisco, ajoutez **/$PSN.xml** à l’URL du serveur d’approvisionnement.


## <a name="configure-conditional-access"></a>Configurer l’accès conditionnel

L’accès conditionnel est une fonctionnalité Azure Active Directory (Azure AD) qui permet de garantir que les appareils qui accèdent à vos ressources Microsoft 365 sont correctement gérés et sécurisés. La passerelle SIP authentifie les appareils SIP auprès d’Azure AD. Par conséquent, si votre organisation utilise l’accès conditionnel pour les appareils du réseau d’entreprise, elle doit exclure les adresses IP suivantes :

- Amérique du Nord :
    - USA Est : 52.170.38.140
    - USA Ouest : 40.112.144.212
-   Région EMEA :
    - Ue Nord : 40.112.71.149
    - UE Ouest : 40.113.112.67
-   Région APAC :
    - Australie Est : 20.92.120.71
    - Australie Sud-Est : 13.73.115.90

Pour plus d’informations, consultez [les plages d’adresses IP](/azure/active-directory/conditional-access/location-condition#ip-address-ranges).

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>Approvisionner et inscrire des appareils SIP en tant que téléphones de zone commune

> [!NOTE]
> Un appareil SIP doit être intégré à la passerelle SIP avant de pouvoir être inscrit.

Pour simplifier vos tâches, vous pouvez inscrire des appareils SIP dans le Centre d’administration Teams un par un ou par lots. Voici comment procéder :

1. Connectez-vous au [**Centre d’administration Teams**](https://admin.teams.microsoft.com).

2. Sélectionnez **appareils** > **Teams appareils SIP**.

3. En haut à droite, sélectionnez **Actions** > **Provisionner les appareils** et effectuez l’une des étapes suivantes :

  - **Pour approvisionner un appareil :**

     a. Sous **En attente de l’activation**, **sélectionnez Ajouter**.

     b. Dans le volet **Ajouter des adresses MAC** , entrez **l’adresse MAC** et **l’emplacement** de l’appareil, puis **sélectionnez Appliquer**.
     
     c. Sous **Attendre l’activation**, sélectionnez l’appareil que vous venez d’ajouter, puis **sélectionnez Générer le code de vérification**.
     
     d. Dans le volet **Approvisionner des appareils** , sous **Code de vérification**, notez le code de vérification de l’appareil SIP.

   - **Pour provisionner de nombreux appareils :**

     a. Sous **En attente de l’activation**, à droite, sélectionnez **Exporter** (icône Microsoft Excel).
     
     b. Dans le volet **Approvisionner des appareils** , sous **Charger plusieurs adresses MAC**, sélectionnez **télécharger un modèle**.
     
     c. Enregistrez **Template_Provisioning.csv** sur votre ordinateur et renseignez les champs **ID MAC** et **Emplacement** .
    
     d. Dans le volet **Approvisionner des appareils** , **sélectionnez Charger plusieurs adresses MAC**. 

     E. À droite du volet **Charger des adresses MAC** , **sélectionnez Sélectionner un fichier, puis sélectionnez** le **fichierTemplate_Provisioning.csv** qui contient vos données.

     F. Dans le volet **Approvisionner des appareils** , sous **En attente d’activation**, sélectionnez un appareil, puis **sélectionnez Générer le code de vérification** pour générer un code de vérification unique pour chaque appareil approvisionné. Notez le code de vérification pour chaque appareil SIP.

4. Sur l’appareil SIP, composez le code de fonctionnalité d’inscription suivi du code de vérification. Sur l’appareil SIP, composez le code \*de fonctionnalité d’inscription 55* (utilisé par la passerelle SIP pour la validation du code de vérification unique de l’inscription), suivi du code de vérification généré dans teams Administration Center pour cet appareil particulier. Par exemple, si le code de vérification est 123456, composez \*55\*123456 pour inscrire l’appareil.

5.  Dans le volet **Approvisionner des appareils** , sous **En attente de connexion**, sélectionnez **Déconnecter**.

6. Dans la boîte de dialogue **Se connecter à un utilisateur** , copiez ou notez le code d’appairage de l’appareil SIP.

7. Accédez à [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin), puis, sous **Entrer du code**, entrez le code d’appairage de l’appareil SIP, puis sélectionnez **Suivant**.

8. Dans **la page de** connexion Microsoft, dans le **champ Email ou téléphone**, entrez l’adresse e-mail de l’appareil SIP, puis sélectionnez **Suivant**.

9. Dans la page **Mot de passe** , entrez le mot de passe de l’adresse e-mail de l’appareil SIP, puis **sélectionnez Se connecter**.

10. Dans la page **Passerelle Des appareils SIP Teams** , sélectionnez **Continuer**.

## <a name="how-to-sign-in-and-sign-out"></a>Comment se connecter et se déconnecter

Seule la connexion locale est prise en charge pour les appareils personnels des utilisateurs. Pour déconnecter un appareil du centre Administration, procédez comme suit :

1. Connectez-vous au [**Centre d’administration Teams**](https://admin.teams.microsoft.com).

2. Sélectionnez **appareils** > **Teams appareils SIP**.

3. À droite, sélectionnez un appareil SIP, puis **déconnectez-vous**.


### <a name="user-pairing-and-sign-in"></a>Association d’utilisateurs et connexion

Pour associer un appareil SIP après l’authentification de l’utilisateur à l’aide des informations d’identification d’entreprise, un utilisateur doit :

1. Appuyez sur **Se connecter** sur le téléphone SIP pour afficher l’URL d’authentification et le code de jumelage. Le code d’appairage respecte le temps. S’il expire, l’utilisateur doit appuyer de **nouveau** sur le téléphone et redémarrer le processus de connexion.

2. Accédez à l’URL d’authentification sur le bureau ou le navigateur mobile de l’utilisateur et utilisez les informations d’identification d’entreprise pour vous connecter.

3. Entrez le code d’appairage affiché sur le téléphone SIP dans l’application d’authentification web pour associer le téléphone SIP au compte de l’utilisateur. Lors d’une connexion réussie, ce qui peut prendre un certain temps, le téléphone SIP affiche le numéro de téléphone et le nom d’utilisateur, si l’appareil le prend en charge.

> [!NOTE]
> L’emplacement de l’appareil affiché sur l’application d’authentification web Azure Active Directory est le centre de données de la passerelle SIP auquel l’appareil est connecté. Les téléphones SIP dans l’étendue ne étant pas compatibles avec OAuth, la passerelle SIP authentifie l’utilisateur via l’application d’authentification web, puis associe l’appareil aux informations d’identification de l’utilisateur. En savoir plus ici : [Plateforme d'identités Microsoft et le flux d’octroi d’autorisation d’appareil OAuth 2.0](/azure/active-directory/develop/v2-oauth2-device-code).

### <a name="sign-out"></a>Déconnexion

Pour se déconnecter, un utilisateur d’appareil peut :

- Appuyez sur **Se déconnecter** sur l’appareil SIP et suivez les étapes décrites sur l’appareil. 

Pour déconnecter un appareil sur le Centre d’administration Teams :

1. Connectez-vous au [**Centre d’administration Teams**](https://admin.teams.microsoft.com).

2. Sélectionnez **appareils** > **Teams appareils SIP**.

3. À droite, dans le volet **appareils SIP** , sélectionnez l’appareil.

4. Dans le **volet Détails** de l’appareil, sélectionnez l’onglet **Détails** , puis en haut à droite dans le menu **Actions** , sélectionnez **Se déconnecter**. 

## <a name="view-and-monitor-sip-devices"></a>Afficher et surveiller les appareils SIP

Vous pouvez afficher et surveiller votre inventaire d’appareils SIP dans le Centre d’administration Teams une fois que les utilisateurs des appareils se sont connectés au moins une fois. Voici comment procéder :

1. Connectez-vous au [Centre d’administration Teams](https://admin.teams.microsoft.com/).

2. Sélectionnez **appareils** > **Teams appareils SIP**. Tous les appareils SIP connectés sont répertoriés à droite.

## <a name="restart-a-sip-device"></a>Redémarrer un appareil SIP

1. Connectez-vous au [Centre d’administration Teams](https://admin.teams.microsoft.com).

2. Sélectionnez **appareils** > **Teams appareils SIP**. 

3. À droite, sélectionnez l’appareil SIP que vous souhaitez redémarrer, puis **sélectionnez Redémarrer**.


> [!NOTE]
> - La suppression d’un appareil SIP de votre locataire n’est actuellement pas disponible dans le Centre d’administration Teams. 
> - L’exécution de la commande dépend de la disponibilité de l’appareil, et elle peut ne pas correspondre à l’état d’exécution indiqué dans le Centre d’administration Teams. Si vous essayez d’activer la passerelle SIP sur un appareil qui ne la prend pas en charge, la commande n’est pas exécutée.

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>Synchroniser les modifications de stratégie sur les appareils SIP pour appliquer des stratégies

Les détails et les stratégies utilisateur sont récupérés sur les appareils SIP lorsque les utilisateurs se connectent. Toutes les modifications de stratégie par la suite pour les utilisateurs connectés seront synchronisées avec l’appareil dans un délai d’une heure. L’inscription des appareils doit être actualisée régulièrement auprès de la passerelle SIP. Les téléphones SIP dépendent de la redirection des appels. L’administrateur doit donc définir l’attribut `AllowCallRedirect` sur `Set-CsTeamsCallingPolicy` `Enabled`.


## <a name="set-a-sip-devices-ui-language"></a>Définir la langue d’interface utilisateur d’un appareil SIP

Un appareil SIP peut généralement afficher des informations dans de nombreuses langues. La définition de son langage d’interface utilisateur affecte son interface, y compris les touches logicielles et les messages système de connexion/déconnexion. La définition du langage d’interface utilisateur est effectuée dans le serveur d’approvisionnement, à l’aide du serveur DHCP, ou manuellement en ajoutant une chaîne de code dans l’URL, comme dans les exemples suivants.

Comment définir l’allemand pour les téléphones Polycom, AudioCodes et Yealink :
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Comment définir le japonais pour les téléphones Cisco :
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>Langues prises en charge

|Nom de la langue|Code de langue]
|-------------|-------------|
|Anglais (par défaut)|en       |
|Espagnol      |es           |
|Japonais     |Ja           |
|Allemand       |de           |
|Français       |Fr           |
|Portugais   |Pt           |

> [!Note]
> - Le japonais n’est pas pris en charge par Yealink et partiellement pris en charge par Polycom VVX.
> - Par défaut, le système utilise l’anglais si la langue sélectionnée n’est pas prise en charge par le point de terminaison SIP.
> - Lorsque le paramètre **lang_xx** n’est pas défini via l’URL de provisionnement, l’anglais est utilisé comme langue par défaut.
> - Si **vous vous connectez pour effectuer un appel d’urgence** , le texte d’appel d’urgence n’est pas traduit dans d’autres langues, une version abrégée en anglais uniquement est présentée lors de la **connexion à la presse** sur les modèles de téléphone IP suivants en raison d’une limitation de taille d’écran :
>   - Poly VVX 150, VVX 201
>   - Cisco CP-6821, CP-7811, CP-7821, CP-7841, CP-7861
>   - L’étiquette softkey de messagerie vocale est codée en dur avec du texte de **machine** virtuelle dans toutes les langues pour Poly VVX en raison d’une limitation de la longueur de chaîne.

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams et IPv6

La passerelle SIP prend uniquement en charge IPv4. Le service Microsoft Teams et le client prennent en charge IPv4 et IPv6. Si vous souhaitez contrôler les communications avec Microsoft Teams, utilisez les plages d’adresses IP dans les [URL et les plages d’adresses IP Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="emergency-calling"></a>Appel d’urgence

La passerelle SIP prend en charge les appels d’urgence dynamiques (E911 dynamique) pour les appareils SIP compatibles qui partagent des attributs réseau sur le réseau. Ces attributs sont approvisionnés dans le Centre d’administration Teams et peuvent être une combinaison d’adresses IP locales et de longueur de sous-réseau, ou d’ID de châssis et de numéro de port réseau. Pour les appareils qui ne partagent pas d’attributs d’emplacement, ou si l’emplacement n’est pas résolu dynamiquement pour une raison quelconque, la passerelle SIP continuera à prendre en charge les appels d’urgence en fonction des adresses inscrites. Actuellement, les adresses inscrites ne sont pas prises en charge pour les scénarios de routage direct. Pour plus d’informations sur les appels d’urgence, consultez [Planifier et gérer les appels d’urgence](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing).

## <a name="report-problems-to-microsoft"></a>Signaler des problèmes à Microsoft

Pour signaler des problèmes, contactez [Support Microsoft](https://support.microsoft.com).
