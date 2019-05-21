---
title: Menaces fréquentes pour la sécurité dans l’informatique moderne
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Étant donné que Skype entreprise Server est un système de communication d’entreprise, vous devez tenir compte des attaques courantes de sécurité qui pourraient affecter son infrastructure et ses communications.
ms.openlocfilehash: 31971846f95b98d566166b6336451ecdb71d7ac7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296923"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Menaces fréquentes pour la sécurité dans l’informatique moderne
 
Étant donné que Skype entreprise Server est un système de communication d’entreprise, vous devez tenir compte des attaques courantes de sécurité qui pourraient affecter son infrastructure et ses communications.
  
## <a name="compromised-key-attack"></a>Attaque par clé compromise

Une clé est un code ou un nombre secret utilisé pour chiffrer, déchiffrer ou valider des informations confidentielles. Il existe deux clés sensibles utilisées dans l’infrastructure à clé publique (PKI) qui doivent être considérées comme suit: 
  
- la clé privée que possède chaque détenteur de certificat ;
    
- la clé de session, utilisée après l’identification et l’échange de clé de session entre les partenaires communiquant entre eux.
    
Une attaque par clé compromise se produit lorsqu’un intrus parvient à identifier la clé privée ou la clé de session. Lorsque l’intrus parvient à déterminer la clé, il s’en sert pour déchiffrer des données chiffrées, à l’insu de l’expéditeur des données.
  
Skype entreprise Server utilise les fonctionnalités de PKI dans le système d’exploitation Windows Server pour protéger les données clés utilisées pour le chiffrement des connexions TLS (Transport Layer Security). Les clés utilisées pour le chiffrement multimédia sont échangées via des connexions TLS.
  
## <a name="network-denial-of-service-attack"></a>Attaque réseau par déni de service

Une attaque par déni de service se produit lorsqu’une personne malveillante empêche des utilisateurs valides de travailler et d’utiliser le réseau normalement. Pour ce faire, elle inonde le service avec des demandes légitimes qui submergent l’utilisation du service par les utilisateurs légitimes. Lors d’une attaque de ce type, la personne malveillante peut :
  
- envoyer des données non valides à des applications et des services exécutés sur le réseau faisant l’objet de l’attaque, afin de perturber leur exécution normale ;
    
- envoyer un volume de trafic important, de manière à surcharger le système jusqu’à ce que celui-ci cesse de fonctionner ou nécessite beaucoup de temps pour répondre aux demandes légitimes ;
    
- masquer les signes d’attaque ;
    
- empêcher les utilisateurs d’accéder aux ressources réseau.
    
## <a name="eavesdropping-sniffing-snooping"></a>Attaque par écoute (Eavesdropping)

Une attaque par écoute peut se produire lorsqu’une personne malveillante parvient à accéder au chemin d’accès des données d’un réseau et qu’elle peut ainsi surveiller et lire le trafic. Cette attaque est également appelée reniflage (« sniffing ») ou surveillance (« snooping »). Si le trafic consiste en du texte simple, l’intrus peut lire le trafic lorsqu’il accède au chemin d’accès des données. Par exemple, une attaque peut être lancée en contrôlant un routeur sur le chemin de données. 
  
La recommandation et le paramètre de trafic par défaut dans Skype entreprise Server consiste à utiliser Mutual TLS (Mutual TLS) entre les serveurs de confiance et TLS du client vers le serveur. Cette mesure de protection rend ce type d’attaque difficile, voire impossible, durant le laps de temps pendant lequel une conversation donnée peut être attaquée. Le protocole TLS authentifie toutes les parties et chiffre le trafic. Ceci n’empêche pas les attaques par écoute, mais l’intrus ne peut pas lire le trafic à moins que le chiffrement ne soit rompu.
  
Le protocole TURN (Traversal Using Relay NAT) n’exige pas que le trafic soit chiffré. Les informations acheminées sont protégées par l’intégrité des messages. Bien qu’elles puissent faire l’objet d’une attaque par écoute, les informations acheminées (autrement dit, les adresses IP et le port) peuvent être extraites directement, en observant simplement les adresses source et de destination des paquets. Le service Edge A/V s’assure que les données sont valides en vérifiant l’intégrité du message à l’aide d’une clé dérivée de plusieurs éléments, dont un mot de passe TURN, qui n’est jamais transmise en texte en clair. Si le protocole SRTP (Secure Real Time Protocol) est utilisé, le trafic multimédia est également chiffré.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Usurpation d’identité (adresse IP et identité d’identification de l’appelant)

L’usurpation d’identité intervient lorsque l’attaquant détermine et utilise le numéro de téléphone d’un utilisateur valide (ID d’appelant) ou d’une adresse IP d’un réseau, d’un ordinateur ou d’un composant réseau sans être autorisé à le faire. Une attaque réussie permet à l’attaquant de fonctionner comme s’il s’agissait d’une entité identifiée habituellement par le numéro de téléphone (ID d’appelant) ou l’adresse IP.

Dans le cadre de Skype entreprise Server, l’usurpation d’adresse IP intervient uniquement si un administrateur a réalisé les deux opérations suivantes:
  
- configuré des connexions qui prennent uniquement en charge le protocole TCP (Transmission Control Protocol), ce qui n’est pas recommandé car les communications TCP ne sont pas chiffrées ;
    
- marqué les adresses IP de ces connexions en tant qu’hôtes approuvés.
    
Ce problème est moins grave pour les connexions TLS (Transport Layer Security), car TLS authentifie toutes les parties et chiffre le trafic. L’utilisation du protocole TLS empêche une personne malveillante d’usurper une adresse IP sur une connexion spécifique (par exemple, les connexions Mutual TLS). Toutefois, une personne malveillante risque de falsifier l’adresse du serveur DNS utilisé par Skype entreprise Server. Toutefois, étant donné que l’authentification dans Skype entreprise est effectuée à l’aide de certificats, l’attaquant ne dispose pas d’un certificat valide requis pour usurper une des parties de la communication.

D’un autre côté, l’usurpation d’identité d’identification de l’appelant intervient lorsque vous avez établi une ligne SIP entre un fournisseur, une passerelle PSTN ou un autre système PBX et Skype entreprise Server. Dans ces cas, Skype entreprise Server n’offre aucune protection contre l’usurpation d’identité d’identification de l’appelant. Cela signifie que l’utilisateur de Skype entreprise peut recevoir un appel à partir du SIP Trunk avec un identifiant d’appelant usurpé qui affiche le numéro de téléphone ou le nom d’affichage (si la recherche du numéro inverse s’applique) d’un autre utilisateur Skype entreprise. Une telle protection devrait être appliquée sur le côté du fournisseur, sur PSTN ou sur une passerelle PBX.
  
## <a name="man-in-the-middle-attack"></a>Attaque de l’intercepteur (« man-in-the-middle »)

Une attaque par homme-au-milieu se produit lorsqu’un attaquant redirige la communication entre les deux utilisateurs par le biais de l’ordinateur de l’attaquant sans connaissance des deux utilisateurs communicants. L’intrus peut surveiller et lire le trafic avant de l’acheminer vers le destinataire concerné. Chacun des utilisateurs envoie et reçoit du trafic vers/de l’intrus, alors qu’il pense communiquer avec l’utilisateur concerné uniquement. Cela peut se produire si une personne malveillante modifie les services de domaine Active Directory pour ajouter son serveur en tant que serveur approuvé, ou si elle modifie DNS (Domain Name System) pour faire en sorte que les clients se connectent au serveur via l’ordinateur de l’intrus à l’origine de l’attaque. Une attaque de l’intercepteur peut également affecter le trafic multimédia entre deux clients. Néanmoins, dans Skype entreprise Server, l’audio, la vidéo et le partage d’application, les flux sont chiffrés avec SRTP, à l’aide des clés de chiffrement négociées entre les homologues utilisant le protocole SIP (Session Initiation Protocol) sur TLS. Les serveurs tels que le serveur de conversation de groupe utilisent le protocole HTTPS pour sécuriser le trafic.
  
## <a name="rtp-replay-attack"></a>Attaque par relecture RTP

Une attaque par relecture se produit lorsqu’une transmission multimédia valide entre deux correspondants est interceptée, puis retransmise à des fins malveillantes. SRTP est utilisé dans le cadre d’un protocole de signalisation sécurisé qui protège les transmissions des attaques par relecture en permettant au destinataire de conserver un index de Paquets RTP déjà reçus et de comparer chaque nouveau paquet aux personnes déjà répertoriées dans l’index.
  
## <a name="spim"></a>Messages instantanés indésirables (Spim)

Le spim correspond à des messages instantanés commerciaux ou des demandes d’abonnement aux informations de présence non sollicités. S’il ne constitue pas à lui seul une menace envers le réseau, il peut néanmoins perturber les activités des utilisateurs et avoir un impact négatif sur la disponibilité des ressources et la production. Il représente donc un risque potentiel pour le réseau. Prenons le cas d’utilisateurs qui génèrent du spim en s’envoyant mutuellement des demandes. Un utilisateur peut en bloquer un autre pour ne plus recevoir de messages instantanés indésirables. Toutefois, dans le cas de la fédération, il peut s’avérer difficile de faire face à une attaque de spim coordonnée, à moins de désactiver la fédération pour le partenaire.
  
## <a name="viruses-and-worms"></a>Virus et vers

Un virus est une unité de code ayant pour finalité la reproduction d’unités de code similaires supplémentaires. Pour fonctionner, un virus a besoin d’un hôte, par exemple un fichier, un e-mail ou un programme. Aworm est une unité de code dont l’objectif est de reproduire d’autres unités de code similaires, mais elle n’a pas besoin d’un hôte. Les virus et les vers apparaissent principalement lors des transferts de fichiers entre clients ou lorsque des URL sont envoyées par d’autres utilisateurs. Si vous avez un virus sur votre ordinateur, il peut, par exemple, utiliser votre identité et envoyer des messages instantanés en votre nom.
  
## <a name="personally-identifiable-information"></a>Informations d’identification personnelle

Grâce à Skype entreprise Server, il est possible de divulguer des informations sur un réseau public qui peuvent être liées à une personne. Ces informations appartiennent à deux catégories :
  
- **Données de présence améliorées** Les données de présence améliorées sont des informations que les utilisateurs peuvent choisir de partager ou de ne pas partager sur un lien vers un partenaire fédéré ou avec des contacts au sein d’une organisation. Elles ne sont pas partagées avec les utilisateurs d’un réseau public de messagerie instantanée. Selon les stratégies de groupe en vigueur et la configuration du client, l’administrateur système peut contrôler ces informations. Dans Skype entreprise Server, le mode de confidentialité Enhanced presence peut être configuré pour un utilisateur individuel afin d’éviter que les utilisateurs de Skype entreprise ne se trouvent pas dans la liste de contacts de l’utilisateur, en consultant les informations de présence de l’utilisateur. Le mode de confidentialité Enhanced presence n’empêche pas les utilisateurs de Microsoft Office Communicator 2007 et Microsoft Office Communicator 2007 R2 d’afficher les informations de présence d’un utilisateur. Pour plus d’informations sur le déploiement du client et de la présence, reportez-vous à la rubrique [déploiement de clients pour Skype entreprise Server](../../deploy/deploy-clients/deploy-clients.md) et [planification de la messagerie instantanée et de la présence dans Skype entreprise Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Données obligatoires** Des données obligatoires sont nécessaires pour le bon fonctionnement du serveur ou du client et ne sont pas sous le contrôle de l’administration du client ou du système. Il s’agit d’informations nécessaires au niveau du serveur ou du réseau aux fins de routage, de maintenance de l’État et de signalisation.
    
Les tableaux suivants répertorient les données exposées sur un réseau public.
  
**Données de présence enrichie**

|**Données divulguées**|**Paramètres possibles**|
|:-----|:-----|
|Données personnelles  <br/> |Nom, Fonction, Société, Adresse électronique, Fuseau horaire  <br/> |
|Numéros de téléphone  <br/> |Bureau, Mobile, Domicile  <br/> |
|Informations de calendrier  <br/> |Libre/Occupé(e), notification d’absence du bureau, détails de réunion (pour les personnes ayant accès à votre calendrier)  <br/> |
|Statut de présence  <br/> |Absent(e), Disponible, Occupé(e), Ne pas déranger, Hors connexion  <br/> |
   
**Données obligatoires**


| **Données divulguées** | **Exemples d’informations**                            |
|:-------------------|:---------------------------------------------------|
| Adresse IP  <br/>  | Adresse réelle de l’ordinateur ou adresse traduite via NAT  <br/> |
| URI SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

