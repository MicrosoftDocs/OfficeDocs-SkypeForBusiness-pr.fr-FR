---
title: Utiliser PowerShell pour les tâches dans le menu Sécurité
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Résumé : Skype Entreprise Server panneau de contrôle au mappage de cmdlet pour le menu Sécurité.'
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824901"
---
# <a name="security"></a>Sécurité

Cet article décrit comment des résultats similaires à ceux de l’élément de **menu** Sécurité du Panneau de contrôle hérité peuvent être obtenus à l’aide d’cmdlets.

Cet article décrit les sous-menus suivants :

- [Sécurité](#security)
  - [Registrar](#registrar)
  - [Service Web](#web-service)
  - [Stratégie de code confidentiel](#pin-policy)

## <a name="registrar"></a>Registrar

**Le** sous-menu REGISTRAR permet aux administrateurs de gérer les serveurs proxy via les paramètres de configuration du serveur proxy. Ces paramètres, qui peuvent être appliqués à la fois au niveau de l’étendue globale et de l’étendue Service (bien que seuls les services serveur Edge et serveur d’inscriptions) permettent de contrôler des éléments tels que les protocoles d’authentification qui peuvent être utilisés par les points de terminaison clients et si la compression sera ou non utilisée sur les connexions de serveurs proxy entrants et sortants.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **REGISTRAR** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---

> **Scénario 1 :** liste de toutes les configurations de proxy

   ![Configuration du proxy de liste](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Exemple***

```powershell
 Get-CsProxyConfiguration
```

---

> **Scénario 2 :** créer une configuration de proxy

   ![Créer une configuration de proxy](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***Exemple***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **Scénario 3 :** obtenir les détails d’une configuration de proxy choisie

   ![Obtenir la configuration du proxy](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***Exemple***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **Scénario 4 :** Supprimer les configurations de proxy choisies

   ![Supprimer la configuration du proxy](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***Exemple***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **Scénario 5 :** mettre à jour une configuration de proxy

   ![Mettre à jour la configuration du proxy](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***Exemple***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Service Web

L’élément de sous-menu **SERVICE WEB** sous **Sécurité** permet aux administrateurs de gérer les paramètres de configuration des services Web dans toute l’organisation . Cela inclut la gestion du développement de groupes, des paramètres de certificat et des méthodes d’authentification autorisées. Étant donné que les administrateurs peuvent configurer différents paramètres au niveau de l’étendue globale, du site et du service (bien que ce soit le seul service de services Web), vous pouvez personnaliser les fonctionnalités des services Web pour différents utilisateurs et différents emplacements.

Considérons les différentes tâches qu’un utilisateur peut effectuer sur **WEB SERVICE** et les cmdlets Skype Entreprise que ces tâches m’indiquent.

---
> **Scénario 1 :** liste de toutes les configurations de service web

   ![Configuration du service Web de liste](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Exemple***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **Scénario 2 :** créer une configuration de service web

   ![Nouvelle configuration de service Web](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***Exemple***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **Scénario 3 :** obtenir les détails d’une configuration de service web choisie

   ![Obtenir la configuration du service Web](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***Exemple***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Scénario 4 :** Supprimer les configurations de service web choisies

   ![Supprimer la configuration du service Web](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***Exemple***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **Scénario 5 :** mettre à jour une configuration de service web

   ![Mettre à jour la configuration du service Web](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***Exemple***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>Stratégie de code confidentiel

Les administrateurs peuvent utiliser la stratégie de code **confidentiel pour** gérer les propriétés d’authentification par code confidentiel . par exemple, on peut spécifier la longueur minimale d’un code confidentiel et déterminer si l’on autorisera les code confidentiels qui utilisent des « modèles courants » tels que des chiffres consécutifs (par exemple, un code confidentiel comme 123456)

Considérons les différentes tâches qu’un utilisateur peut effectuer sur la STRATÉGIE de code confidentiel **et** les Skype Entreprise cmdlets sur Skype Entreprise ces tâches.

---

> **Scénario 1 :** Liste de toutes les stratégies de code confidentiel

   ![Stratégie de code confidentiel de liste](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Exemple***

```powershell
 Get-CsPinPolicy
```

---

> **Scénario 2 :** créer une stratégie de code confidentiel

   ![Créer une stratégie de code confidentiel](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***Exemple***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **Scénario 3 :** obtenir les détails d’une stratégie de code confidentiel choisie

   ![Obtenir une stratégie de code confidentiel](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***Exemple***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **Scénario 4 :** Supprimer les stratégies de code confidentiel choisies

   ![Supprimer une stratégie de code confidentiel](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***Exemple***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **Scénario 5 : mettre** à jour une stratégie de code confidentiel

   ![Mettre à jour la stratégie de code confidentiel](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***Exemple***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
