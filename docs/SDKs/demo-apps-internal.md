---
title: Demo apps (internal)
excerpt: >-
  Internal reference for demo applications showcasing Recurly Engage SDK
  integrations.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This page lists internal demo apps for various platforms to help CSMs/TAMs and internal teams validate and demonstrate Recurly Engage SDK functionality.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Demo apps require access keys (see <strong>Key details</strong>).
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Demo Apps** page provides download links and repositories for internal demonstration applications covering Roku, React Native, iOS/tvOS, and Android/Fire platforms.

## Roku

Package (v1.0.27): [Download SDK](https://assets.redfastlabs.com/sdk/roku-demo-1.0.27.zip)

## React Native

Repository: [GitHub – Recurly Engage React Native Demo](https://github.com/redfast/redfast-sdk-react-native)

## iOS/tvOS

Repository: [GitHub – Recurly Engage Apple SDK Demo](https://github.com/redfast/redfast-sdk-apple)

## Android/Fire

Repository: [GitHub – Recurly Engage Android SDK Demo](https://github.com/redfast/redfast-sdk-android)

> 📘 CSM/TAM:
>
> Provide necessary API keys and auth tokens to customers (all platforms except Roku). Installation details: [Demo App Installation Guide](https://www.notion.so/redfast/Apple-Android-React-Native-Demo-App-Installation-10c52c0a764980a4a4ffc5c34e739dd8?pvs=4)