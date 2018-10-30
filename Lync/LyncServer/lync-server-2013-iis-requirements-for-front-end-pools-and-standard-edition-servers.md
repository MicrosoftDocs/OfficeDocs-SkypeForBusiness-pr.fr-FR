---
title: "LS 2013 : Conf. req. pr serv. Int. (IIS), pools front., serv. Standard Edition"
TOCTitle: Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg399038(v=OCS.15)
ms:contentKeyID: 49299192
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour les serveurs Standard Edition, les serveurs frontaux et les directeurs, le programme d’installation de Lync Server 2013 crée des répertoires virtuels dans les services Internet (IIS) pour :

  - permettre aux utilisateurs de télécharger des fichiers du service de carnet d’adresses ;

  - permettre aux clients d’obtenir des mises à jour ;

  - activer les conférences ;

  - permettre aux utilisateurs de télécharger le contenu de réunions ;

  - permettre aux utilisateurs de développer des groupes de distribution ;

  - activer la téléconférence ;

  - activer les fonctionnalités du service Response Group.

De plus, le programme d’installation de la mise à jour cumulative de novembre 2011 pour Lync Server 2010 crée des répertoires virtuels dans les services Internet (IIS) pour les besoins suivants :

  - Sur les serveurs frontaux ou les serveurs Standard Edition afin de prendre en charge les fonctionnalités de mobilité, telles que la messagerie instantanée et la présence, sur les appareils mobiles

  - Sur les serveurs frontaux ou les serveurs Standard Edition et sur les Directeurs afin de permettre aux appareils mobiles de découvrir automatiquement les ressources de mobilité

> [!NOTE]  
> Si vous déployez la mobilité, nous vous recommandons d’utiliser les services Internet (IIS) 7.5. Le programme d’installation du service de mobilité de Lync Server définit certains indicateurs ASP.NET afin d’améliorer les performances. Les services Internet (IIS) 7.5 sont installés par défaut sur Windows Server 2008 R2 et le programme d’installation du service de mobilité modifie automatiquement les paramètres ASP.NET. Si vous utilisez les services Internet (IIS) 7.0 sur Windows Server 2008, vous devez modifier manuellement ces paramètres.

Lync Server nécessite l’installation des modules des services Internet (IIS) suivants :

> [!IMPORTANT]  
> Si votre organisation vous oblige à placer les services Internet (IIS) et tous les services web sur une unité autre que l’unité système, vous pouvez modifier le chemin d’accès de l’emplacement d’installation des fichiers Lync Server fdans la boîte de dialogue Installation. Si vous installez les fichiers d’installation à cet emplacement, dont OCSCore.msi, les autres fichiers Lync Server seront également déployés sur cette unité. Pour plus d’informations sur le déplacement du composant INETPUB déployé par le Gestionnaire de serveur Windows lors de l’installation des services Internet (IIS), reportez-vous à <a href="http://go.microsoft.com/fwlink/?linkid=216888" class="uri">http://go.microsoft.com/fwlink/?linkid=216888</a>.

  - Contenu statique

  - Document par défaut

  - Erreurs HTTP

  - ASP.NET

  - Extensibilité .NET

  - Extensions ISAPI (Internet Server API)

  - Filtres ISAPI

  - Journalisation HTTP

  - Outils de journalisation

  - Suivi

  - Authentification Windows

  - Filtrage des demandes

  - Compression du contenu statique

  - Compression du contenu dynamique

  - Console de gestion des services Internet (IIS)

  - Scripts et outils de gestion des services Internet (IIS)

  - Authentification anonyme (installée par défaut lors de l’installation des services Internet \[IIS\])

  - Authentification par mappage de certificat client

Le tableau ci-dessous répertorie les URI des répertoires virtuels pour l’accès interne et les ressources du système de fichiers auxquelles ils se rapportent.

### Répertoires virtuels pour l’accès interne

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>URI du répertoire virtuel</th>
<th>Se rapporte à</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Serveur de carnet d’adresses</p></td>
<td><p>https:// <em>&lt;Nom de domaine complet interne&gt;</em> /ABS/int/Handler</p></td>
<td><p>Emplacement des fichiers téléchargés du serveur de carnet d’adresses pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Service de découverte automatique</p></td>
<td><p>https:// <em>&lt;Nom de domaine complet interne&gt;</em> /Autodiscover</p></td>
<td><p>Emplacement du service de découverte automatique de Lync Server qui localise les ressources de mobilité pour les utilisateurs d’appareils mobiles internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour du client</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /AutoUpdate/Int</p></td>
<td><p>Emplacement des fichiers de mise à jour pour les clients internes basés sur ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>Conf</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /Conf/Int</p></td>
<td><p>Emplacement des ressources de conférence pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Mises à jour des périphériques</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /DeviceUpdateFiles_Int</p></td>
<td><p>Emplacement des fichiers de mise à jour des appareils de communications unifiées pour les appareils de communications unifiées internes.</p></td>
</tr>
<tr class="even">
<td><p>Réunion</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /etc/place/null</p></td>
<td><p>Emplacement du contenu de réunion pour les utilisateurs internes.</p></td>
</tr>
<tr class="odd">
<td><p>Service de mobilité</p></td>
<td><p>https:// <em>&lt;Nom de domaine complet interne&gt;</em> /Mcx</p></td>
<td><p>Emplacement des ressources du service de mobilité pour les utilisateurs d’appareils mobiles internes.</p></td>
</tr>
<tr class="even">
<td><p>Développement de groupes et service de requête sur le web du carnet d’adresses</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /GroupExpansion/int/service.asmx</p></td>
<td><p>Emplacement du service web qui active le développement des groupes pour les utilisateurs internes. C’est également l’emplacement du service de requête sur le web du carnet d’adresses qui fournit les informations de liste d’adresses globale aux clients internes Lync MobileMicrosoft Lync 2010 Mobile.</p></td>
</tr>
<tr class="odd">
<td><p>Téléconférence</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /PhoneConferencing/Int</p></td>
<td><p>Emplacement des données de téléconférence pour les utilisateurs internes.</p></td>
</tr>
<tr class="even">
<td><p>Mises à jour des périphériques</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /RequestHandler</p></td>
<td><p>Emplacement du Gestionnaire des demandes du service web de mise à jour des périphériques qui permet aux appareils de communications unifiées internes de télécharger des journaux et de vérifier l’existence de mises à jour.</p></td>
</tr>
<tr class="odd">
<td><p>application Response Group</p></td>
<td><p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /RgsConfig</p>
<p>http:// <em>&lt;Nom de domaine complet interne&gt;</em> /RgsClients</p></td>
<td><p>Emplacement de l’outil de configuration du service Response Group.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Pour les pools de serveurs frontaux dans une configuration consolidée, vous devez déployer les services Internet (IIS) pour pouvoir ajouter des serveurs au pool.

> [!security]  
> Vous devez utiliser le composant logiciel enfichable d’administration des services Internet (IIS) pour attribuer le certificat utilisé par le serveur de composants web des services Internet (IIS).
