---
title: Salles Microsoft Teams sécurité des données
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
description: Découvrez comment sécuriser vos Salles Microsoft Teams appareils mobiles.
ms.openlocfilehash: 7043b49406b0865ef38108519040374d792ac1dd
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306109"
---
# <a name="microsoft-teams-rooms-security"></a>Salles Microsoft Teams sécurité des données

Microsoft collabore avec nos partenaires pour fournir une solution sécurisée qui ne nécessite aucune action supplémentaire pour sécuriser les Salles Microsoft Teams. Cet article traite de nombreuses fonctionnalités de sécurité qui se trouvent dans salles Teams.

> [!NOTE]
> Salles Microsoft Teams ne doivent pas être traités comme des stations de travail classiques d’utilisateurs. Non seulement les cas d’utilisation sont très différents, mais les profils de sécurité par défaut sont également très différents.
> Cet article s’applique Salles Microsoft Teams appareils en cours d’Windows.

Des données d’utilisateur final limitées sont stockées sur salles Teams. Les données des utilisateurs finaux peuvent être stockées dans les fichiers journaux à des finaux de résolution des problèmes et d’assistance uniquement. À aucun moment un participant à une réunion ne peut utiliser salles Teams copier des fichiers sur le disque dur ou se connecter en tant que lui-même. Aucune donnée de l’utilisateur final n’est transférée ou accessible par le Salles Microsoft Teams appareil.

Même si les utilisateurs finaux ne peuvent pas placer de fichiers sur salles Teams disque dur, Microsoft Defender est toujours activé. salles Teams performances de l’entreprise sont testées avec Microsoft Defender. La désactivation de ce logiciel ou l’ajout d’un logiciel de sécurité de point de terminaison peut entraîner des résultats imprévisibles et une dégradation potentielle du système.

## <a name="hardware-security"></a>Sécurité matérielle

Dans un salles Teams de calcul, un module de calcul central est Windows 10 IoT Entreprise édition. Chaque module de calcul certifié doit avoir une solution d’attache sécurisée, un logement de verrouillage de sécurité (par exemple, le verrouillage ) et des mesures de sécurité d’accès par port I/O pour empêcher la connexion d’appareils non autorisés. Vous pouvez également désactiver des ports spécifiques via une configuration UEFI (Unified Extensible Firmware Interface).

Chaque module de calcul certifié doit être fourni avec la technologie compatible TPM (Trusted Platform Module) 2.0 activée par défaut. La gestion des données TPM sert à chiffrer les informations de connexion du salles Teams ressource.

Le démarrage sécurisé est activé par défaut. Le démarrage sécurisé est une norme de sécurité développée par les membres du secteur des PC pour s’assurer qu’un démarrage d’appareil n’utilise que des logiciels de confiance par le fabricant d’ordinateurs (OEM). Lorsque le PC démarre, le microprogramme vérifie la signature de chaque logiciel de démarrage, y compris les pilotes de microprogramme UEFI (également appelés roms d’options), les applications EFI et le système d’exploitation. Si les signatures sont valides, le pc démarre et le microprogramme donne le contrôle au système d’exploitation. Pour plus d’informations, voir [Démarrage sécurisé.](/windows-hardware/design/device-experiences/oem-secure-boot)

L’accès aux paramètres UEFI n’est possible qu’en attachant un clavier physique et une souris. Cela empêche d’accéder à UEFI via la console tactile salles Teams ainsi que tout autre écran tactile connecté à salles Teams.

La protection DMA (Kernel Direct Memory Access) est un paramètre Windows 10 activé sur salles Teams. Avec cette fonctionnalité, le système d’exploitation et le microprogramme système protègent le système contre les attaques DMA malveillantes et inattendues pour tous les appareils capables de DMA :

- Pendant le démarrage.

- Contre la DMA malveillante par les appareils connectés à des ports internes/externes facilement accessibles, tels que les emplacements du PCIe M.2 et Thunderbolt 3, pendant l’runtime du système d’exploitation.

salles Teams’intégrité du code protégé par l’hyperviseur (HVCI). Credential Guard est une des fonctionnalités fournies par HVCI. Credential Guard offre les avantages suivants :

- **Sécurité matérielle** NTLM, Kerberos et le Gestionnaire d’informations d’identification tirez parti des fonctionnalités de sécurité de la plateforme, notamment le démarrage sécurisé et la virtualisation, pour protéger les informations d’identification.

- **Les informations d’identification** dérivées et d’autres secrets Windows NTLM et Kerberos sont exécutés dans un environnement protégé isolé du système d’exploitation en cours d’exécution.

- **Meilleure protection contre les menaces persistantes avancées** Lorsque les informations d’identification de domaine du Gestionnaire d’informations d’identification, NTLM et Kerberos dérivées sont protégées à l’aide de la sécurité basée sur la virtualisation, les techniques et outils d’attaque par vol d’informations d’identification utilisés dans de nombreuses attaques ciblées sont bloqués. Les programmes malveillants en cours d’exécution dans le système d’exploitation avec des privilèges d’administration ne peuvent pas extraire des secrets protégés par une sécurité basée sur la virtualisation.

## <a name="software-security"></a>Sécurité logicielle

Une fois que Microsoft Windows, salles Teams automatiquement à un compte d’Windows local nommé Skype. Le compte Skype n’a pas de mot de passe. Pour sécuriser la Skype compte, les étapes suivantes sont prises.

> [!IMPORTANT]
> Ne modifiez pas le mot de passe ou ne modifiez pas le compte d’Skype’utilisateur local. Cela permet d’salles Teams la salles Teams automatiquement.

L Salles Microsoft Teams’application s’exécute à l’aide de la fonctionnalité Accès affecté Windows 10 1903 et ultérieure. L’accès affecté est une fonctionnalité Windows 10 qui limite les points d’entrée d’application exposés à l’utilisateur. C’est ce qui active le mode d’une seule application kiosk. Grâce à Shell Lanceur, salles Teams est configuré comme un appareil borne qui exécute une application de bureau Windows l’interface utilisateur. L Salles Microsoft Teams appil remplace l’shell par défaut (explorer.exe) qui s’exécute généralement lorsqu’un utilisateur se connecte. En d’autres termes, le shell traditionnel de l’Explorateur n’est pas lancé. Cela réduit considérablement la surface de Salles Microsoft Teams à l’intérieur Windows. Pour plus d’informations, voir Configurer des bornes et des panneaux [numériques Windows éditions de bureau.](/windows/configuration/kiosk-methods)

Si vous décidez d’exécuter une analyse de sécurité ou un centre de sécurité Internet sur salles Teams, l’analyse peut uniquement s’exécuter dans le contexte d’un compte d’administrateur local, car le compte d’utilisateur Skype ne prend pas en charge l’exécution d’applications autres que l’application salles Teams. Bon nombre des fonctionnalités de sécurité appliquées au contexte d’utilisateur Skype ne s’appliquent pas aux autres utilisateurs locaux et, par conséquent, ces analyses de sécurité n’entraînent pas le verrouillage complet de la sécurité appliqué au compte Skype. Par conséquent, il n’est pas recommandé d’exécuter une analyse locale sur salles Teams. Toutefois, si vous le souhaitez, vous pouvez exécuter des tests de déficit externe. Pour cette raison, nous vous recommandons d’exécuter des tests de déficit extérieur sur salles Teams appareils au lieu d’exécuter des analyses locales.

En outre, des stratégies de verrouillage sont appliquées afin de limiter l’utilisation des fonctionnalités non administratives. Un filtre clavier est activé pour intercepter et bloquer les combinaisons de claviers éventuellement en cours qui ne sont pas couvertes par les stratégies Accès affecté. Seuls les utilisateurs ayant des droits d’administration locaux ou de domaine sont autorisés à se Windows pour gérer salles Teams. Ces stratégies ainsi que d’autres appliquées Windows sur Salles Microsoft Teams appareils sont évaluées et testées en permanence pendant le cycle de vie du produit.

## <a name="account-security"></a>Sécurité du compte

salles Teams incluent un compte d’administration nommé « Administrateur » avec un mot de passe par défaut. Nous vous recommandons vivement de modifier le mot de passe par défaut dès que possible une fois la configuration terminée.

Le compte d’administrateur n’est pas requis pour une opération appropriée salles Teams appareils mobiles et peut être renommé ou même supprimé. Toutefois, avant de supprimer le compte d’administrateur, veillez à configurer un autre compte d’administrateur local configuré avant de supprimer celui qui est salles Teams appareils mobiles. Pour plus d’informations sur la modification du mot de passe d’un compte Windows local à l’aide d’outils Windows intégrés ou de PowerShell, voir les sections suivantes :

- [Modifier ou réinitialiser votre mot Windows passe](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Vous pouvez également importer des comptes de domaine dans le groupe administrateur Windows local. Vous pouvez le faire pour Azure AD comptes à l’aide d’Intune. Pour plus d’informations, [voir Stratégie CSP – Groupes restreints.](/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!NOTE]
> Si vous utilisez des consoles Crestron, assurez-vous également de mettre à jour le mot de passe administrateur sur la console et sur le module de calcul. Pour plus d’informations, contactez Crestron.

> [!CAUTION]
> Si vous supprimez ou désactivez le compte administrateur avant d’octroyer des autorisations d’administrateur local à un autre compte local ou de domaine, vous risquez de perdre la possibilité d’administrer le salles Teams appareil. Dans ce cas, vous devrez réinitialiser l’appareil à ses paramètres d’origine et terminer le processus de configuration à nouveau.

N’accordez pas d’autorisations d’administrateur local au Skype utilisateur.

Windows Configuration Designer peut être utilisé pour créer des packages Windows 10 approvisionnement. Outre la modification du mot de passe administrateur local, vous pouvez également modifier le nom de l’ordinateur et vous inscrire à Azure Active Directory. Pour plus d’informations sur la création d’un package Windows Configuration Designer, voir [Packages d’approvisionnement pour Windows 10.](/windows/configuration/provisioning-packages/provisioning-packages)

Vous devez créer un compte de ressource pour chaque salles Teams appareil afin qu’il puisse se Teams. Vous ne pouvez pas utiliser l’authentification à deux facteurs ou multifacteur avec ce compte. La nécessité d’utiliser un deuxième facteur empêcherait le compte de se connecter automatiquement à l’salles Teams’application après un redémarrage. Toutefois, vous pouvez activer l’authentification moderne pour plus de sécurité pour ce compte. En outre, des stratégies d’accès conditionnel basées sur l’emplacement peuvent être déployées pour le compte de ressource afin d’empêcher que vous ne vous y soyez pas ouvert. Pour plus d’informations, voir [Utiliser la condition d’emplacement dans une stratégie d’accès conditionnel](/azure/active-directory/conditional-access/location-condition)

Nous vous recommandons de créer le compte de ressource Azure AD, si possible. Bien qu’un compte synchronisé puisse fonctionner avec salles Teams dans des déploiements hybrides, ces comptes synchronisés ont souvent des difficultés à se salles Teams et peuvent être difficiles à résoudre. Si vous choisissez d’utiliser un service de fédération tiers pour authentifier les informations d’identification du compte de ressource, assurez-vous que la personne IDP tierce répond avec l’attribut `wsTrustResponse` set to `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Sécurité réseau

En règle générale, salles Teams a la même exigences réseau que n’importe quel Microsoft Teams client. L’accès via les pare-feu et autres appareils de sécurité est le même pour les salles Teams que pour tout autre client Microsoft Teams sécurité. Spécifiques aux salles Teams, les catégories répertoriées comme « requises » pour Teams doivent être ouvertes sur votre pare-feu. salles Teams a également besoin d’accéder à Windows jour, Microsoft Store et Microsoft Intune (si vous utilisez Microsoft Intune pour gérer vos appareils). Pour obtenir la liste complète des ADRESSES ET URL requises pour Salles Microsoft Teams, voir :

- **Microsoft Teams** [Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows à jour** [Configurez WSUS](/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Microsoft Store** [conditions préalables pour l’éducation et Microsoft Store pour Entreprises l’éducation](/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [points de terminaison réseau pour Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Si vous utilisez le composant Salles Microsoft Teams services gérés d’Salles Microsoft Teams Premium, vous devez également vous assurer que salles Teams pouvez accéder aux URL suivantes :

- agent.rooms.microsoft.com
- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- mmrstgnoamiot.azure-devices.net
- mmrstgnoamstor.blob.core.windows.net
- mmrprodapaciot.azure-devices.net
- mmrprodapacstor.blob.core.windows.net
- mmrprodemeaiot.azure-devices.net
- mmrprodemeastor.blob.core.windows.net
- mmrprodnoamiot.azure-devices.net
- mmrprodnoamstor.blob.core.windows.net

salles Teams est configuré pour assurer automatiquement l’application de correctifs avec les dernières mises Windows jour, y compris les mises à jour de sécurité. salles Teams installe les mises à jour en attente tous les jours à partir de 02:00 à l’aide d’une stratégie locale pré-définie. Il n’est pas nécessaire d’utiliser des outils supplémentaires pour déployer et appliquer Windows mises à jour. L’utilisation d’outils supplémentaires pour déployer et appliquer des mises à jour peut retarder l’installation des correctifs Windows et donc entraîner un déploiement moins sécurisé. L salles Teams appappe de déploiement est déployée à l’aide du Microsoft Store. Si la licence de vos appareils est Salles Microsoft Teams Standard, toutes les nouvelles versions de l’application sont installées automatiquement pendant le processus de mise à jour des correctifs nocturnes. Si vos appareils sont concédés sous licence Salles Microsoft Teams Premium et inscrits au service géré microsoft, les nouvelles versions de l’application salles Teams sont installées selon votre plan de déploiement défini.

salles Teams fonctionnent avec la plupart des protocoles de sécurité réseau ou 802.1X. Toutefois, nous ne pouvons pas tester les salles Teams toutes les configurations de sécurité réseau possibles. Par conséquent, si des problèmes de performances peuvent être pointés vers des problèmes de performances réseau, vous devrez peut-être désactiver ces protocoles s’ils sont configurés dans votre organisation.

Pour optimiser les performances optimales des médias en temps réel, nous vous recommandons vivement de configurer Teams trafic de médias pour contourner les serveurs proxy et autres périphériques de sécurité réseau. Les médias en temps réel sont sensibles à la latence, et les serveurs proxy et les périphériques de sécurité réseau peuvent considérablement dégrader la qualité audio et vidéo des utilisateurs. Par ailleurs, étant Teams multimédias en ligne sont déjà chiffrés, la transmission du trafic via un serveur proxy n’offre aucun avantage. Pour plus d’informations, voir Mise en réseau vers le cloud : [l’œuvre d’un](/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) architecture qui traite des recommandations réseau pour améliorer les performances des médias avec Microsoft Teams et Salles Microsoft Teams.

> [!IMPORTANT]
> salles Teams ne prend pas en charge les serveurs proxy authentifiés.

salles Teams’appareils n’ont pas besoin de se connecter à un réseau laN interne. Envisagez de placer des salles Teams dans un segment réseau sécurisé avec un accès Internet direct. Si votre laN interne devient compromise, les opportunités d’attaque du vecteur d’salles Teams sont réduites.

Nous vous recommandons vivement de connecter vos salles Teams à un réseau câblé. L’utilisation de réseaux sans fil sur salles Teams appareils mobiles n’est ni recommandée ni certifiée. Certaines fonctionnalités de connectivité, telles que Wi-Fi Sense, sont désactivées par défaut.

Les fonctionnalités de jointité de proximité salles Teams reposent sur Bluetooth. Toutefois, l Bluetooth implémentation en cours sur salles Teams appareils externes n’autorise pas une connexion d’appareil externe à salles Teams appareil. Bluetooth’utilisation de la technologie salles Teams appareils mobiles est actuellement limitée à la publicité des balises et aux connexions proximales invités. Le `ADV_NONCONN_INT` type d’unité de données du protocole (PDU) est utilisé dans la balise publicitaire. Ce type de PDU s’agit d’appareils non connectables qui annoncent des informations sur le périphérique d’écoute. Il n’est pas Bluetooth le coupage d’appareil dans le cadre de ces fonctionnalités. Des informations supplémentaires sur Bluetooth protocoles d’entreprise sont Bluetooth site web du [groupe SIG.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
