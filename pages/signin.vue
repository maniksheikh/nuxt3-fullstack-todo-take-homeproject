<template>
  <div class="bg-[#e7ddff] h-[100vh]">
    <div class="bg-[#000] text-white mx-auto text-center justify-center mt-24 items-center w-[480px] overflow-hidden p-10 font-medium rounded-lg border border-l-white">
    <h1 class="font-bold py-5">Sign In</h1>
    <div>
      <div class="flex justify-center gap-4 py-12 border border-gray-100">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="18"
        height="18"
        viewBox="0 0 256 262"
      >
        <path
          fill="#4285F4"
          d="M255.878 133.451c0-10.734-.871-18.567-2.756-26.69H130.55v48.448h71.947c-1.45 12.04-9.283 30.172-26.69 42.356l-.244 1.622l38.755 30.023l2.685.268c24.659-22.774 38.875-56.282 38.875-96.027"
        />
        <path
          fill="#34A853"
          d="M130.55 261.1c35.248 0 64.839-11.605 86.453-31.622l-41.196-31.913c-11.024 7.688-25.82 13.055-45.257 13.055c-34.523 0-63.824-22.773-74.269-54.25l-1.531.13l-40.298 31.187l-.527 1.465C35.393 231.798 79.49 261.1 130.55 261.1"
        />
        <path
          fill="#FBBC05"
          d="M56.281 156.37c-2.756-8.123-4.351-16.827-4.351-25.82c0-8.994 1.595-17.697 4.206-25.82l-.073-1.73L15.26 71.312l-1.335.635C5.077 89.644 0 109.517 0 130.55s5.077 40.905 13.925 58.602l42.356-32.782"
        />
        <path
          fill="#EB4335"
          d="M130.55 50.479c24.514 0 41.05 10.589 50.479 19.438l36.844-35.974C195.245 12.91 165.798 0 130.55 0C79.49 0 35.393 29.301 13.925 71.947l42.211 32.783c10.59-31.477 39.891-54.251 74.414-54.251"
        />
      </svg>
      <button @click.stop="signInWithGoogle">Sign in With Google</button>
    </div>
    </div>
  
    <p class=" flex text-center p-5 mt-6">This site is protected by reCAPTCHA and the Google Privacy Policy and Terms of Service apply</p>
  </div>
  </div>
 
</template>

<script setup>
import { signInWithPopup, GoogleAuthProvider, getAuth } from "firebase/auth";

const signInWithGoogle = async () => {
  const auth = getAuth();
  const provider = new GoogleAuthProvider();
  try {
    await signInWithPopup(auth, provider);
    console.log("Successfully signed in with Google");
    navigateTo('/')
    
  } catch (error) {
    console.error("Error signing in with Google:", error);
  }
};
</script>
  
  <style></style>
  