---
title: "Serveurs proxy pour Skype Entreprise Online"
ms.author: tonysmit
author: tonysmit
ms.date: 11/6/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
description: "Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise."
---

# Serveurs proxy pour Skype Entreprise Online

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Cet article vous orientera dans l'utilisation d'un serveur proxy avec Skype ºEntreprise.
  
## Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne le trafic Skype Entreprise, Microsoft recommande d'éviter d'utiliser un serveur proxy. En effet, cela ne permettra pas de sécuriser davantage Skype Entreprise, car son trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels difficultés altèreront l'expérience tant dans les scénarios Skype Entreprise audio que vidéo, pour lesquels les transmissions en continu en temps réel sont essentielles..
  
## SI vous devez utiliser un serveur proxy

Certaines organisations n'ont aucune option pour ignorer un proxy pour Skype pour le trafic d'entreprise. Si c'est le cas pour vous, les problèmes mentionnés ci-dessus doivent rester à l'esprit.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP 
    
- L'application des autres recommandations de nos directives relatives à la mise en réseau :
    
  - [Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimisation de votre réseau pour Skype Entreprise Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## Fournisseurs de serveurs proxy avec options de configuration ou prise en charge de Skype Entreprise intégrées

Cette section contiendra des informations sur les fournisseurs de serveurs proxy qui vendent des produits ou services dont l'utilisation avec le trafic Skype Entreprise s'est avérée efficace.
  
- Dans le cas d'organisations utilisant **Bluecoat Proxy Solutions**, un nouveau microprogramme a été publié et permet de résoudre divers problèmes liés aux éléments suivants :
    
  - Interception SSL
    
  - Vérifications OCSP/SRL
    
  - SIP sur TLS
    
  - Prise en charge de TURN
    
    La prise en charge native de Bluecoat pour Skype Entreprise peut être facilement activée et permet l'identification du trafic pertinent et une gestion adéquate.L'optimisation de l'authentification, des signaux et du flux du trafic multimédia est ainsi assurée et vous bénéficiez d'une excellente expérience utilisateur sans être préoccupé par d'éventuels problèmes liés à la sécurité.
    
    Consultez le lien suivant si Bluecoat Proxy fait partie de la topologie de votre réseau
    
- https://support.Symantec.com/en_US/article.DOC9757.HTML
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

