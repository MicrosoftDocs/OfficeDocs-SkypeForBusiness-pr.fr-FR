---
title: Sécurité des salles Microsoft Teams
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Découvrez comment sécuriser vos appareils Salle Microsoft Teams.
ms.openlocfilehash: d9968af4f386ed68d9a931d834082ba5362c5c33
ms.sourcegitcommit: 380cd74c08cd34e1c3f73f5c0f51da4ae2674f6f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49880870"
---
# <a name="microsoft-teams-rooms-security"></a>Sécurité des salles Microsoft Teams

Microsoft collabore avec nos partenaires pour fournir une solution sécurisée qui ne nécessite aucune action supplémentaire pour sécuriser les salles Microsoft Teams. Cet article traite de nombreuses fonctionnalités de sécurité disponibles dans les salles Teams.

> [!NOTE]
> Les salles Microsoft Teams ne doivent pas être traitées comme une station de travail d’utilisateur final classique. Non seulement les cas d’utilisation sont très différents, mais les profils de sécurité par défaut sont également très différents.

Des données limitées sur les utilisateurs finux sont stockées dans des salles Teams. Les données des utilisateurs finaux peuvent être stockées dans les fichiers journaux à des finaux de résolution des problèmes et d’assistance uniquement. Les participants à une réunion ne peuvent à aucun moment, à l’aide des salles Teams, copier des fichiers sur le disque dur ou se connecter en tant que tels. Aucune donnée d’utilisateur final n’est transférée ou accessible par l’appareil Salles Microsoft Teams.

Même si les utilisateurs finaux ne peuvent pas placer de fichiers sur un disque dur Salles Teams, Microsoft Defender est toujours activé. Les performances des salles Teams sont testées avec Microsoft Defender. La désactivation de ce logiciel ou l’ajout d’un logiciel de sécurité de point de terminaison peut entraîner des résultats imprévisibles et une dégradation potentielle du système.

## <a name="hardware-security"></a>Sécurité matérielle

Dans un environnement de salles d’équipe, un module de calcul central exécute l’édition IoT Enterprise de Windows 10. Chaque module de calcul certifié doit avoir une solution de montage sécurisée, un logement de verrouillage de sécurité (par exemple, le verrouillage ) et des mesures de sécurité d’accès par port I/O pour empêcher la connexion d’appareils non autorisés. Vous pouvez également désactiver des ports spécifiques via une configuration UEFI (Unified Extensible Firmware Interface).

Chaque module de calcul certifié doit être fourni avec la technologie compatible TPM (Trusted Platform Module) 2.0 activée par défaut. La gestion des données TPM sert à chiffrer les informations de connexion du compte de ressource Salles Teams.

Le démarrage sécurisé est activé par défaut. Le démarrage sécurisé est une norme de sécurité développée par les membres du secteur des PC pour s’assurer qu’un démarrage d’appareil n’utilise que des logiciels de confiance par le fabricant d’équipement d’origine (OEM). Lorsque le PC démarre, le microprogramme vérifie la signature de chaque élément du logiciel de démarrage, y compris les pilotes de microprogramme UEFI (également appelés roms d’options), les applications EFI et le système d’exploitation. Si les signatures sont valides, le pc démarre et le microprogramme donne le contrôle au système d’exploitation. Pour plus d’informations, voir [Démarrage sécurisé.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

L’accès aux paramètres UEFI n’est possible qu’en attachant un clavier physique et une souris. Cela empêche d’accéder à UEFI via la console tactile Salles d’équipes, ainsi que tout autre écran tactile joint à Salles Teams.

La protection DMA (Kernel Direct Memory Access) est un paramètre Windows 10 activé dans les salles Teams. Avec cette fonctionnalité, le système d’exploitation et le microprogramme système protègent le système contre les attaques DMA malveillantes et inattendues pour tous les appareils capables de DMA :

- Pendant le démarrage.

- Contre la DMA malveillante par les appareils connectés à des ports internes/externes facilement accessibles, tels que les emplacements du PCIe M.2 et Thunderbolt 3, pendant l’runtime du système d’exploitation.

Les salles Teams activent également l’intégrité du code protégé par un hyperviseur (HVCI). Credential Guard est une des fonctionnalités fournies par HVCI. Credential Guard offre les avantages suivants :

- **Sécurité matérielle** NTLM, Kerberos et le Gestionnaire d’informations d’identification tirez parti des fonctionnalités de sécurité de la plateforme, notamment le démarrage sécurisé et la virtualisation, pour protéger les informations d’identification.

- **Sécurité basée sur la virtualisation** Les informations d’identification dérivées Windows NTLM et Kerberos, ainsi que d’autres secrets, sont exécutés dans un environnement protégé isolé du système d’exploitation en cours d’exécution.

- **Meilleure protection contre les menaces persistantes avancées** Lorsque les informations d’identification de domaine du Gestionnaire d’informations d’identification, NTLM et Kerberos dérivées sont protégées à l’aide de la sécurité basée sur la virtualisation, les techniques d’attaque par vol d’informations d’identification et les outils utilisés dans de nombreuses attaques ciblées sont bloqués. Les programmes malveillants en cours d’exécution dans le système d’exploitation avec des privilèges d’administration ne peuvent pas extraire des secrets protégés par la sécurité basée sur la virtualisation.

## <a name="software-security"></a>Sécurité logicielle

Après les boots Microsoft Windows, Salles Teams se signe automatiquement sur un compte d’utilisateur Windows local nommé Skype. Le compte Skype n’a pas de mot de passe. Pour sécuriser la session du compte Skype, les étapes suivantes sont prises.

> [!IMPORTANT]
> Ne modifiez pas le mot de passe ou le compte d’utilisateur Skype local. Cette opération peut empêcher Salles Teams de se se trouver automatiquement.

L’application Salles Microsoft Teams s’exécute à l’aide de la fonctionnalité Accès affecté de Windows 10 1903 et ultérieure. L’accès affecté est une fonctionnalité de Windows 10 qui limite les points d’entrée d’application exposés à l’utilisateur. C’est ce qui active le mode d’une seule application kiosk. À l’Lanceur de ligne de commandes, Salles Teams est configurée comme un appareil de borne qui exécute une application de bureau Windows comme interface utilisateur. L’application Salles Microsoft Teams remplace l’shell par défaut (explorer.exe) qui s’exécute généralement lorsqu’un utilisateur se connecte. En d’autres termes, le shell traditionnel de l’Explorateur n’est pas lancé. Cela réduit considérablement la vulnérabilité des salles Microsoft Teams dans Windows. Pour plus d’informations, voir [Configurer des bornes et des panneaux numériques sur les éditions de bureau Windows.](https://docs.microsoft.com/windows/configuration/kiosk-methods)

Si vous décidez d’exécuter une analyse de sécurité ou un centre de sécurité Internet sur les salles Teams, l’analyse peut uniquement s’exécuter dans le contexte d’un compte d’administrateur local, car le compte d’utilisateur Skype ne prend pas en charge l’exécution d’applications autres que l’application Salles Teams. Bon nombre des fonctionnalités de sécurité appliquées au contexte utilisateur Skype ne s’appliquent pas aux autres utilisateurs locaux et, par conséquent, ces analyses de sécurité n’entraînent pas le verrouillage complet de la sécurité appliqué au compte Skype. Par conséquent, il n’est pas recommandé d’exécuter une analyse locale dans les salles Teams. Toutefois, si vous le souhaitez, vous pouvez exécuter des tests de déficit externe. Pour cette raison, nous vous recommandons d’exécuter des tests de déficit extérieur sur les appareils Teams Rooms au lieu d’exécuter des analyses locales.

En outre, des stratégies de verrouillage sont appliquées afin de limiter l’utilisation des fonctionnalités non administratives. Un filtre clavier est activé pour intercepter et bloquer les combinaisons de claviers potentiellement incursées par les stratégies Accès affecté. Seuls les utilisateurs disposent de droits d’administration locaux ou de domaine sont autorisés à se connecter à Windows pour gérer les salles d’équipe. Ces stratégies ainsi que d’autres appliquées à Windows sur les appareils Microsoft Teams Rooms sont évaluées et testées en permanence pendant le cycle de vie des produits.

## <a name="account-security"></a>Sécurité du compte

Les appareils Salle Teams incluent un compte d’administration nommé « Administrateur » avec un mot de passe par défaut. Nous vous recommandons vivement de modifier le mot de passe par défaut dès que possible une fois la configuration terminée.

Le compte d’administrateur n’est pas nécessaire pour le bon fonctionnement des appareils Salles Teams et peut être renommé ou même supprimé. Toutefois, avant de supprimer le compte d’administrateur, veillez à configurer un autre compte d’administrateur local configuré avant de supprimer celui qui est configuré avec les appareils Salles d’équipe. Pour plus d’informations sur la modification du mot de passe d’un compte Windows local à l’aide des outils Windows intégrés ou de PowerShell, voir les sections suivantes :

- [Modifier ou réinitialiser votre mot de passe Windows](https://support.microsoft.com/windows/change-or-reset-your-windows-password-8271d17c-9f9e-443f-835a-8318c8f68b9c)
- [Set-LocalUser](https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1#example-2--change-the-password-on-an-account)

Vous pouvez également importer des comptes de domaine dans le groupe d’administrateurs Windows local. Vous pouvez le faire pour les comptes Azure AD à l’aide d’Intune. Pour plus d’informations, [voir Stratégie CSP – Groupes restreints.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-restrictedgroups)

> [!CAUTION]
> Si vous supprimez ou désactivez le compte administrateur avant d’octroyer des autorisations d’administrateur local à un autre compte local ou de domaine, vous risquez de perdre la possibilité d’administrer l’appareil Salles d’équipe. Dans ce cas, vous devrez réinitialiser l’appareil à ses paramètres d’origine et terminer le processus de configuration à nouveau.
>
> N’accordez pas d’autorisations d’administrateur local au compte d’utilisateur Skype.

Windows Configuration Designer peut être utilisé pour créer des packages de mise en service Windows 10. Outre la modification du mot de passe administrateur local, vous pouvez également modifier le nom de l’ordinateur et vous inscrire à Azure Active Directory. Pour plus d’informations sur la création d’un package de mise en service Windows Configuration Designer, voir [Packages d’approvisionnement pour Windows 10.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Vous devez créer un compte de ressource pour chaque appareil Salles Teams afin qu’il puisse se connecte à Teams. Vous ne pouvez pas utiliser l’authentification à deux facteurs ou multifacteur avec ce compte. La mise en place d’un deuxième facteur empêche le compte de se connecter automatiquement à l’application Salles d’équipe après un redémarrage. Toutefois, vous pouvez activer l’authentification moderne pour plus de sécurité pour ce compte. En outre, des stratégies d’accès conditionnel basées sur l’emplacement peuvent être déployées pour le compte de ressource afin d’empêcher qu’un emplacement non approbé ne soit entré dans le compte. Pour plus d’informations, voir [Utiliser la condition d’emplacement dans une stratégie d’accès conditionnel](https://docs.microsoft.com/azure/active-directory/conditional-access/location-condition)

Nous vous recommandons de créer le compte de ressource dans Azure AD, si possible. Bien qu’un compte synchronisé puisse fonctionner avec des salles Teams dans les déploiements hybrides, ces comptes synchronisés ont souvent des difficultés à se brancher aux salles d’équipe et peuvent être difficiles à résoudre. Si vous choisissez d’utiliser un service de fédération tiers pour authentifier les informations d’identification du compte de ressource, assurez-vous que la personne IDP tierce répond avec l’attribut `wsTrustResponse` set to `urn:oasis:names:tc:SAML:1.0:assertion` .

## <a name="network-security"></a>Sécurité réseau

En règle générale, les salles Teams ont la même exigences réseau que n’importe quel client Microsoft Teams. L’accès via les pare-feu et autres appareils de sécurité est identique pour les salles Teams et pour tout autre client Microsoft Teams. Spécifiques aux salles Teams, les catégories répertoriées comme « obligatoires » pour Teams doivent être ouvertes sur votre pare-feu. Les salles Teams ont également besoin d’accéder à Windows Update, au Microsoft Store et à Microsoft Intune (si vous utilisez Microsoft Intune pour gérer vos appareils). Pour obtenir la liste complète des adresses IPS et DES URL requises pour les salles Microsoft Teams, voir :

- **URL et** plages d’adresses IP Microsoft Teams [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams)
- **Windows Update** [Configure WSUS](https://docs.microsoft.com/windows-server/administration/windows-server-update-services/deploy/2-configure-wsus#211-connection-from-the-wsus-server-to-the-internet)
- **Conditions préalables** du Microsoft Store [pour Entreprises et Éducation](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business#proxy-configuration)
- **Microsoft Intune** [Network Enpoints pour Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)

Si vous utilisez le composant des services gérés des salles Microsoft Teams de Microsoft Teams Salles Premium, vous devez également vous assurer que les salles Teams peuvent accéder aux URL suivantes :

- global.azure-devices-provisioning.net
- gj3ftstorage.blob.core.windows.net
- gj3ft-hub.azure-devices.net
- iothubsgagwt5wgvwg6.azure-devices.net
- blobssgagwt5wgvwg6.blob.core.windows.net
- prod-48.westus.logic.azure.com
- prod-08.westus.logic.azure.com
- prod-62.westus.logic.azure.com
- prod-65.westus.logic.azure.com
- prod-05.westus.logic.azure.com

Les salles Teams sont configurées pour rester automatiquement mises à jour correctifs avec les dernières mises à jour Windows, y compris les mises à jour de sécurité. Les salles Teams installent les mises à jour en attente tous les jours à partir de 02:00 à l’aide d’une stratégie locale pré-définie. Il n’est pas nécessaire d’utiliser des outils supplémentaires pour déployer et appliquer Windows Update. L’utilisation d’outils supplémentaires pour déployer et appliquer des mises à jour peut retarder l’installation des correctifs Windows et donc entraîner un déploiement moins sécurisé. L’application Salles Teams est déployée à l’aide du Microsoft Store. Si la licence de vos appareils est microsoft Teams Rooms Standard, toutes les nouvelles versions de l’application sont installées automatiquement pendant le processus de mise à jour des correctifs nocturnes. Si vos appareils sont concédés sous licence avec Microsoft Teams Rooms Premium et inscrits au service géré Microsoft, les nouvelles versions de l’application Salles d’équipe sont installées selon votre plan de déploiement défini.

Les appareils Salles Teams fonctionnent avec la plupart des protocoles de sécurité 802.1X ou réseau. Toutefois, nous ne pouvons pas tester les salles Teams par rapport à toutes les configurations de sécurité réseau possibles. Par conséquent, si des problèmes de performances peuvent être pointés vers des problèmes de performances réseau, vous devrez peut-être désactiver ces protocoles s’ils sont configurés dans votre organisation.

Pour optimiser les performances optimales des médias en temps réel, nous vous recommandons vivement de configurer le trafic de médias Teams pour contourner les serveurs proxy et autres périphériques de sécurité réseau. Les médias en temps réel sont sensibles à la latence, et les serveurs proxy et les périphériques de sécurité réseau peuvent considérablement dégrader la qualité audio et vidéo des utilisateurs. De plus, étant donné que les médias Teams sont déjà chiffrés, il n’y a aucun avantage à transmettre le trafic via un serveur proxy. Pour plus d’informations, voir Mise en réseau vers le cloud : [l’un](https://docs.microsoft.com/microsoft-365/solutions/networking-design-principles?view=o365-worldwide) des concepteurs propose des recommandations réseau pour améliorer les performances des médias avec Microsoft Teams et les salles Microsoft Teams.

> [!IMPORTANT]
> Salles Teams ne prend pas en charge les serveurs proxy authentifiés.

Les appareils Salles Teams n’ont pas besoin de se connecter à un réseau laN interne. Envisagez de placer les salles Teams dans un segment réseau sécurisé avec un accès Internet direct. Si votre laN interne devient compromis, les opportunités d’attaque vers les salles Teams seront réduites.

Nous vous recommandons vivement de connecter vos appareils Salles d’équipe à un réseau câblé. L’utilisation de réseaux sans fil sur les appareils teams rooms n’est ni recommandée ni certifiée. Certaines fonctionnalités de connectivité, telles que Wi-Fi Sense, sont désactivées par défaut.

L’adhésion à la proximité et les autres fonctionnalités de salles d’équipe s’appuient sur Bluetooth. Toutefois, l Bluetooth implémentation complète sur les appareils Salles d’équipe ne permet pas d’établir une connexion d’appareil externe à un appareil Salles d’équipe. Bluetooth’utilisation de la technologie sur les appareils Salle Teams est actuellement limité aux balises publicitaires et aux connexions proximales invites. Le `ADV_NONCONN_INT` type d’unité de données du protocole (PDU) est utilisé dans la balise publicitaire. Ce type de PDU s’agit d’appareils non connectables qui annoncent des informations sur le périphérique d’écoute. Il n’est pas Bluetooth le coupage d’appareil dans le cadre de ces fonctionnalités. Des informations supplémentaires sur Bluetooth protocoles d’entreprise sont Bluetooth site web [de sig.](https://www.bluetooth.com/blog/bluetooth-low-energy-it-starts-with-advertising/)
