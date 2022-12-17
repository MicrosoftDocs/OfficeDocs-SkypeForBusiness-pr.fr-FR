---
title: Salles Microsoft Teams sur la sécurité Windows
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Découvrez comment sécuriser vos Salles Microsoft Teams sur les appareils Windows.
ms.openlocfilehash: f7774b43542885118bd66eb09cf1d30049b84425
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438467"
---
# <a name="microsoft-teams-rooms-on-windows-security"></a>Salles Microsoft Teams sur la sécurité Windows

Microsoft travaille avec nos partenaires pour fournir une solution sécurisée qui ne nécessite pas d’actions supplémentaires pour sécuriser Salles Microsoft Teams sur Windows. Cet article décrit la plupart des fonctionnalités de sécurité disponibles dans salles Teams sur Windows.

Pour plus d’informations sur la sécurité sur salles Teams sur les appareils Android, consultez [Salles Microsoft Teams sur la sécurité Android](security-android.md).

> [!NOTE]
> Salles Microsoft Teams ne doivent pas être traités comme une station de travail d’utilisateur final classique. Non seulement les cas d’usage sont très différents, mais les profils de sécurité par défaut sont également très différents.
> Cet article s’applique aux appareils Salles Microsoft Teams s’exécutant sur Windows.

Les données des utilisateurs finaux limitées sont stockées sur salles Teams. Les données de l’utilisateur final peuvent être stockées dans les fichiers journaux à des fins de dépannage et de support uniquement. À aucun moment, un participant à une réunion utilisant salles Teams copier des fichiers sur le disque dur ou se connecter en tant que lui-même. Aucune donnée de l’utilisateur final n’est transférée ou accessible par l’appareil Salles Microsoft Teams.

Même si les utilisateurs finaux ne peuvent pas placer de fichiers sur un disque dur salles Teams, Microsoft Defender est toujours activé. salles Teams performances sont testées avec Microsoft Defender. La désactivation ou l’ajout d’un logiciel de sécurité de point de terminaison peut entraîner des résultats imprévisibles et une dégradation potentielle du système.

## <a name="hardware-security"></a>Sécurité matérielle

Dans un environnement salles Teams, il existe un module de calcul central qui s’exécute Windows 10 IoT Entreprise édition. Chaque module de calcul certifié doit disposer d’une solution de montage sécurisée, d’un emplacement de verrouillage de sécurité (par exemple, verrou Kensington) et de mesures de sécurité d’accès aux ports d’E/S pour empêcher la connexion d’appareils non autorisés. Vous pouvez également désactiver des ports spécifiques via la configuration UEFI (Unified Extensible Firmware Interface).

Chaque module de calcul certifié doit être fourni avec la technologie compatible TPM (Trusted Platform Module) 2.0 activée par défaut. TPM est utilisé pour chiffrer les informations de connexion pour le compte de ressource salles Teams.

Le démarrage sécurisé est activé par défaut. Le démarrage sécurisé est une norme de sécurité développée par les membres de l’industrie des PC pour s’assurer qu’un appareil démarre uniquement à l’aide d’un logiciel approuvé par le fabricant d’équipement d’origine (OEM). Au démarrage du PC, le microprogramme vérifie la signature de chaque élément du logiciel de démarrage, y compris les pilotes de microprogramme UEFI (également appelés RoMs Option), les applications EFI et le système d’exploitation. Si les signatures sont valides, le PC démarre et le microprogramme donne le contrôle au système d’exploitation. Pour plus d’informations, consultez [Démarrage sécurisé](/windows-hardware/design/device-experiences/oem-secure-boot).

L’accès aux paramètres UEFI n’est possible qu’en attachant un clavier et une souris physiques. Cela empêche d’accéder à UEFI via la console tactile salles Teams, ainsi que tout autre écran tactile attaché à salles Teams.

La protection d’accès direct à la mémoire du noyau (DMA) est un paramètre Windows 10 activé sur salles Teams. Avec cette fonctionnalité, le système d’exploitation et le microprogramme du système protègent le système contre les attaques DMA malveillantes et involontaires pour tous les appareils compatibles DMA :

- Pendant le processus de démarrage.

- Contre les DMA malveillants par des appareils connectés à des ports compatibles DMA internes/externes facilement accessibles, tels que les emplacements PCIe M.2 et Thunderbolt 3, pendant l’exécution du système d’exploitation.

salles Teams active également l’intégrité du code protégé par l’hyperviseur (HVCI). L’une des fonctionnalités fournies par HVCI est Credential Guard. Credential Guard offre les avantages suivants :

- **Sécurité matérielle** NTLM, Kerberos et Credential Manager tirent parti des fonctionnalités de sécurité de la plateforme, notamment le démarrage sécurisé et la virtualisation, pour protéger les informations d’identification.

- **Sécurité basée sur la virtualisation** Les informations d’identification dérivées de Windows NTLM et Kerberos et d’autres secrets s’exécutent dans un environnement protégé isolé du système d’exploitation en cours d’exécution.

- **Meilleure protection contre les menaces persistantes avancées** Lorsque les informations d’identification du domaine Du gestionnaire d’informations d’identification, les informations d’identification dérivées de NTLM et kerberos sont protégées à l’aide d’une sécurité basée sur la virtualisation, les techniques et outils d’attaque de vol d’informations d’identification utilisés dans de nombreuses attaques ciblées sont bloqués. Les programmes malveillants s’exécutant dans le système d’exploitation avec des privilèges d’administration ne peuvent pas extraire les secrets protégés par la sécurité basée sur la virtualisation.

## <a name="software-security"></a>Sécurité logicielle

Après Microsoft démarrage de Windows, salles Teams se connecte automatiquement à un compte d’utilisateur Windows local nommé Skype. Le compte Skype n’a pas de mot de passe. Pour sécuriser la session de compte Skype, les étapes suivantes sont effectuées.

> [!IMPORTANT]
> Ne modifiez pas le mot de passe et ne modifiez pas le compte d’utilisateur Skype local. Cela peut empêcher salles Teams de se connecter automatiquement.

L’application Salles Microsoft Teams s’exécute à l’aide de la fonctionnalité Accès affecté disponible dans Windows 10 1903 et versions ultérieures. L’accès affecté est une fonctionnalité dans Windows 10 qui limite les points d’entrée d’application exposés à l’utilisateur. C’est ce qui active le mode kiosque à application unique. À l’aide du lanceur d’interpréteur de commandes, salles Teams est configuré en tant qu’appareil kiosque qui exécute une application de bureau Windows en tant qu’interface utilisateur. L’application Salles Microsoft Teams remplace l’interpréteur de commandes par défaut (explorer.exe) qui s’exécute généralement lorsqu’un utilisateur ouvre une session. En d’autres termes, l’interpréteur de commandes Explorer traditionnel n’est pas lancé du tout. Cela réduit considérablement la surface de vulnérabilité Salles Microsoft Teams dans Windows. Pour plus d’informations, consultez [Configurer des bornes et des connexions numériques sur les éditions de bureau Windows](/windows/configuration/kiosk-methods).

Si vous décidez d’exécuter une analyse de sécurité ou un benchmark CIS (Center for Internet Security) sur salles Teams, l’analyse ne peut s’exécuter que dans le contexte d’un compte d’administrateur local, car le compte d’utilisateur Skype ne prend pas en charge l’exécution d’applications autres que l’application salles Teams. La plupart des fonctionnalités de sécurité appliquées au contexte utilisateur Skype ne s’appliquent pas à d’autres utilisateurs locaux et, par conséquent, ces analyses de sécurité ne font pas apparaître le verrouillage de sécurité complet appliqué au compte Skype. Par conséquent, il n’est pas recommandé d’exécuter une analyse locale sur salles Teams. Toutefois, vous pouvez exécuter des tests d’intrusion externes si vous le souhaitez. Pour cette raison, nous vous recommandons d’exécuter des tests d’intrusion externes sur salles Teams appareils au lieu d’exécuter des analyses locales.

En outre, des stratégies de verrouillage sont appliquées pour limiter l’utilisation de fonctionnalités non administratives. Un filtre de clavier est activé pour intercepter et bloquer les combinaisons de clavier potentiellement non sécurisées qui ne sont pas couvertes par les stratégies d’accès affecté. Seuls les utilisateurs disposant de droits d’administration locaux ou de domaine sont autorisés à se connecter à Windows pour gérer salles Teams. Ces stratégies et d’autres stratégies appliquées à Windows sur Salles Microsoft Teams appareils sont continuellement évaluées et testées pendant le cycle de vie du produit.

## <a name="account-security"></a>Sécurité du compte

salles Teams appareils incluent un compte d’administration nommé « Administration » avec un mot de passe par défaut. Nous vous recommandons vivement de modifier le mot de passe par défaut dès que possible une fois l’installation terminée.

Le compte Administration n’est pas requis pour le bon fonctionnement des appareils salles Teams et peut être renommé ou même supprimé. Toutefois, avant de supprimer le compte Administration, veillez à configurer un autre compte d’administrateur local configuré avant de supprimer celui fourni avec salles Teams appareils. Pour plus d’informations sur la modification d’un mot de passe pour un compte Windows local à l’aide des outils Windows intégrés ou de PowerShell, consultez les rubriques suivantes :

- [Modifier ou réinitialiser votre mot de passe Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser#example-2--change-the-password-on-an-account)

Vous pouvez également importer des comptes de domaine dans le groupe Administrateur Windows local. Vous pouvez le faire pour les comptes Azure AD à l’aide de Intune. Pour plus d’informations, consultez [Fournisseur de services de configuration de stratégie – RestrictedGroups.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> Si vous utilisez des consoles Crestron, veillez également à mettre à jour le mot de passe Administration sur la console ainsi que sur le module de calcul. Pour plus d’informations, contactez Crestron.

> [!CAUTION]
> Si vous supprimez ou désactivez le compte Administration avant d’accorder des autorisations d’administrateur local à un autre compte local ou de domaine, vous risquez de perdre la possibilité d’administrer l’appareil salles Teams. Si cela se produit, vous devez réinitialiser l’appareil à ses paramètres d’origine et terminer à nouveau le processus d’installation.

N’accordez pas d’autorisations d’administrateur local au compte d’utilisateur Skype.

Le Concepteur de configuration Windows peut être utilisé pour créer Windows 10 packages d’approvisionnement. En plus de modifier le mot de passe du Administration local, vous pouvez également effectuer des opérations telles que la modification du nom de la machine et l’inscription dans Azure Active Directory. Pour plus d’informations sur la création d’un package d’approvisionnement du Concepteur de configuration Windows, consultez [Mise en service de packages pour Windows 10](/windows/configuration/provisioning-packages/provisioning-packages).

Vous devez créer un compte de ressource pour chaque appareil salles Teams afin qu’il puisse se connecter à Teams. Vous ne pouvez pas utiliser l’authentification à deux facteurs ou multifacteur avec ce compte. L’exigence d’un deuxième facteur empêcherait le compte de se connecter automatiquement à l’application salles Teams après un redémarrage. Toutefois, vous pouvez activer l’authentification moderne pour renforcer la sécurité de ce compte. En outre, les stratégies d’accès conditionnel Azure Active Directory et les stratégies de conformité Intune peuvent être déployées pour sécuriser le compte de ressource. Pour plus d’informations, consultez [Stratégies de conformité des appareils Intune et accès conditionnel pris en charge pour Salles Microsoft Teams](supported-ca-and-compliance-policies.md) et [Conformité de l’accès conditionnel et Intune pour Salles Microsoft Teams](conditional-access-and-compliance-for-devices.md)

Nous vous recommandons de créer le compte de ressource dans Azure AD, si possible. Bien qu’un compte synchronisé puisse fonctionner avec salles Teams dans les déploiements hybrides, ces comptes synchronisés ont souvent des difficultés à se connecter à salles Teams et peuvent être difficiles à résoudre. Si vous choisissez d’utiliser un service de fédération tiers pour authentifier les informations d’identification du compte de ressource, vérifiez que le fournisseur d’identité tiers répond avec l’attribut `wsTrustResponse` défini sur `urn:oasis:names:tc:SAML:1.0:assertion`.

## <a name="network-security"></a>Sécurité réseau

En règle générale, salles Teams a les mêmes exigences réseau que n’importe quel client Microsoft Teams. L’accès via des pare-feu et d’autres appareils de sécurité est le même pour salles Teams que pour tout autre client Microsoft Teams. Spécifique à salles Teams, les catégories répertoriées comme « obligatoires » pour Teams doivent être ouvertes sur votre pare-feu. salles Teams avez également besoin d’accéder à Windows Update, Microsoft Store et Microsoft Intune (si vous utilisez Microsoft Intune pour gérer vos appareils). Pour obtenir la liste complète des adresses IP et url requises pour Salles Microsoft Teams, consultez :

- **URL et** [plages d’adresses IP Microsoft Teams Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Configurer WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Prérequis du magasin Microsoft** [pour l’Microsoft Store pour Entreprises et l’éducation](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **points** de [terminaison réseau Microsoft Intune pour Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Si vous utilisez le composant Salles Microsoft Teams services managés de Salles Microsoft Teams Pro, vous devez également vous assurer que salles Teams pouvez accéder aux URL suivantes :

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

salles Teams est configuré pour conserver automatiquement les correctifs avec les dernières mises à jour Windows, y compris les mises à jour de sécurité. salles Teams installe les mises à jour en attente tous les jours à partir de 02h00 à l’aide d’une stratégie locale prédéfinie. Il n’est pas nécessaire d’utiliser des outils supplémentaires pour déployer et appliquer des Mises à jour Windows. L’utilisation d’outils supplémentaires pour déployer et appliquer des mises à jour peut retarder l’installation des correctifs Windows et entraîner ainsi un déploiement moins sécurisé. L’application salles Teams est déployée à l’aide du Microsoft Store.

<!-- LICENSE-REVIEW If your devices are licensed with Microsoft Teams Rooms Standard, any new versions of the app are automatically installed during the nightly patching process. If your devices are licensed with Microsoft Teams Rooms Premium and enrolled in the Microsoft Managed Service, new versions of the Teams Rooms app are installed per your defined rollout plan. -->

salles Teams appareils fonctionnent avec la plupart des protocoles de sécurité 802.1X ou d’autres protocoles de sécurité réseau. Toutefois, nous ne sommes pas en mesure de tester salles Teams par rapport à toutes les configurations de sécurité réseau possibles. Par conséquent, si des problèmes de performances peuvent être suivis de problèmes de performances réseau, vous devrez peut-être désactiver ces protocoles s’ils sont configurés dans votre organisation.

Pour optimiser les performances des médias en temps réel, nous vous recommandons vivement de configurer le trafic multimédia Teams pour contourner les serveurs proxy et autres périphériques de sécurité réseau. Les médias en temps réel sont très sensibles à la latence et les serveurs proxy et les appareils de sécurité réseau peuvent dégrader considérablement la qualité vidéo et audio des utilisateurs. En outre, étant donné que les médias Teams sont déjà chiffrés, il n’y a aucun avantage tangible à transmettre le trafic via un serveur proxy. Pour plus [d’informations, consultez Mise en réseau (vers le cloud) - Point de vue d’un architecte](/microsoft-365/solutions/networking-design-principles) qui traite des recommandations de réseau pour améliorer les performances des médias avec Microsoft Teams et Salles Microsoft Teams.

> [!IMPORTANT]
> salles Teams ne prend pas en charge les serveurs proxy authentifiés.

salles Teams appareils n’ont pas besoin de se connecter à un réseau lan interne. Envisagez de placer salles Teams dans un segment de réseau sécurisé avec un accès Direct à Internet. Si votre réseau lan interne est compromis, les opportunités de vecteur d’attaque vers salles Teams seront réduites.

Nous vous recommandons vivement de connecter vos appareils salles Teams à un réseau câblé. L’utilisation de réseaux sans fil sur salles Teams appareils n’est ni recommandée ni certifiée. Certaines fonctionnalités de connectivité, telles que Wi-Fi Sense, sont désactivées par défaut.

La jonction de proximité et d’autres fonctionnalités salles Teams s’appuient sur Bluetooth. Toutefois, l’implémentation Bluetooth sur salles Teams appareils n’autorise pas une connexion d’appareil externe à un appareil salles Teams. L’utilisation de la technologie Bluetooth sur les appareils salles Teams est actuellement limitée aux balises publicitaires et aux connexions proximales déclenchées. Le `ADV_NONCONN_INT` type d’unité de données de protocole (PDU) est utilisé dans la balise publicitaire. Ce type de PDU concerne les appareils non connectables qui publient des informations sur l’appareil d’écoute. Il n’existe aucun appairage d’appareils Bluetooth dans le cadre de ces fonctionnalités. Pour plus d’informations sur les protocoles Bluetooth, consultez le [site web bluetooth SIG](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/).
